# Common Infant Pipeline Errors & How to Fix Them


### Neighbors Error in FreeSurfer: 

**Cause**: there are more than 3 voxels between the hemispheres in wm or gm in the segmentations (aseg)

**Fix**: Open aseg in fslview and edit so that there are no more than 3 voxels between the left and right lobes


### Common Readout prior to Exiting due to Error: 

Following message is found prior to many error catching standard out messages.** \
` File "/app/run.py", line 589, in &lt;module>`**


```
	_cli()
  File "/app/run.py", line 80, in _cli
	return interface(**kwargs)
  File "/app/run.py", line 585, in interface
	stage.run(ncpus)
  File "/app/pipelines.py", line 697, in run
	self.teardown(result)
  File "/app/pipelines.py", line 637, in teardown
	self.__class__.__name__)
Exception: error caught during stage: FMRISurface

File "/app/run.py", line 589, in <module>
	_cli()
  File "/app/run.py", line 80, in _cli
	return interface(**kwargs)
  File "/app/run.py", line 585, in interface
	stage.run(ncpus)
  File "/app/pipelines.py", line 697, in run
	self.teardown(result)
  File "/app/pipelines.py", line 637, in teardown
	self.__class__.__name__)
Exception: error caught during stage: FreeSurfer stage
```



### Error in FMRISurface:

ERROR: cifti xml dimensions must be greater than zero


### Missing Expected outputs:

Message: 'missing expected outputs from FreeSurfer' located in `/logs/&lt;STUDY>/&lt;SUB-DIR>/sub-####/sub-####_ses-YYYYMMDD.out`


## Triaging Infant Pipeline Jobs

This guide will walk you through the steps I use when triaging pipeline output. Start with the Slurm logs.


### Information Found in Slurm Logs

Slurm logs are the stdout and stderr files from a Slurm job. The first thing to do when a job no longer is running is check the Slurm logs. Each job will have an output (`.out`) and error (`.err`) Slurm log.

MSI outputs these into a single .out file by default, in the directory you called the submission script from.

Type `scontrol show jobid -dd &lt;job id num> | grep Std` to see the paths for StdErr, StdIn (usually /dev/null), and StdOut for any slurm job currently in the queue.


### Bad Node

Slurm may have scheduled a job on a node on which the pipeline could not run due to one (or more) of these conditions:



* The node was not set up with a scratch folder and we did not have permission to write to.
* The node did not have enough docker image space to load our image.
* Docker was not allowed to run on the node.

Such a job will have failed almost right away. The Slurm logs will be very short and will contain the string `Bad node`. The only thing you can do is to resubmit that job. We can neither fix the node, nor resubmit the job to another node on the fly. But the node will have been added to the list of those to be excluded from our Slurm jobs, so you can be assured that Slurm won't put a subsequent job on the same node.


### Job Failed Before Pipeline Started

The lab's scripts copy the BIDS input, templates, etc. to the node before they run the pipeline. If any of that failed, the Slurm logs should tell you what happened.

Jobs (e.g. Slurm on MSI) will not start if you don’t have write access to where the logs should go


### Job Failed After Pipeline Started

The lab's scripts print the string `RUNNING DOCKER IMAGE` just before calling the pipeline. Before starting each stage, the pipeline prints a line that says `running `followed by the name of the stage.

If the job succeeded (i.e., the pipeline successfully ran all the way through all of the stages), the Slurm logs will have a message that contains `BEGINNING SUCCESS CLEANUP`. If the job failed, the slurm logs will have a message that contains `BEGINNING FAIL CLEANUP`. The most common failures are described here.


### Job Timed Out

If the slurm logs say the job caught an exit code of 140 or 240, the job timed out. Slurm jobs in the exacloud partition time out after 36 hours. (When using the lab's scripts, jobs are allowed to run for just 34 hours so that they have a good chance of copying all the job's data back to lustre1.)

Look higher in the output log to find the last stage that was started. Copy the name of the last stage exactly (case matters). Resubmit the job, starting with that stage.


### Job Exception During Stage

If the job failed but did not time out, the Slurm error log will usually have a line that says `Exception: error caught during stage:` followed by the name of the stage. Note the stage name. That's the stage to start from when you resubmit, _after _you figure out why it failed and fix the problem. This usually requires looking at the pipeline logs. To find them, look at the bottom of the Slurm output log for the string `COPY PROCESSED DATA TO` to find the path to the data for that study. Go to that path and then into the tree for `&lt;subject>/&lt;session>/logs/&lt;stage>`.

When using pipeline logs, remember: cascading errors are of no use to you; you only care about the _first _error that happened in the stage. 


## Troubleshooting Anatomical Errors in Pipeline Logs

The stages that constitute anatomical processing are PreFreeSurfer, FreeSurfer, and PostFreeSurfer.


### No aseg_acpc.nii.gz File

The first stage of the pipeline is PreFreeSurfer. The most crucial file that should come from this stage is its segmentation, aka aseg (`files/T1w/aseg_acpc.nii.gz`).

If PreFreeSurfer failed to make the aseg, look in the PreFreeSurfer error file for the first error. If the error occurred in JLF, resubmit your job. JLF fails intermittently and the job may succeed next time.

If the first error was before JLF, or if you run this multiple times and JLF fails each time, contact the Compute Team for help.


### FreeSurfer failed in mri_normalize

In both of FreeSurfer's logs you will find the string `ERROR: After mri_normalize, &lt;subject id>/mri/T1.mgz does not exist.` In the error file, you will also find the string `Segmentation fault`. This usually occurs when FreeSurfer doesn't like the aseg file.

Note: the use of the word "segmentation" in this case is coincidence. A segmentation fault is a runtime error in the code, for example, trying to divide by 0 will throw a segmentation fault. It just so happens that the segmentation fault can happen in mri_normalize when there is a problem with the aseg file. But it can also happen if there is a problem with the mask. So do not assume that a segmentation fault always refers to the segmentation file. This is one reason I often refer to the segmentation file as the aseg.

If you were using an aseg supplied from an external source (other than PreFreeSurfer) the file might have an orientation or dimension or other property that is not what FreeSurfer expected. Or, if you were using a mask from another source, the aseg file and the mask file might not have the same dimensions. Or it could just be that the aseg was not very good.


## Troubleshooting Task Errors in Pipeline Logs

These pipeline stages process task data: FMRIVolume, FMRISurface, DCANBOLDProcessing. When you go to any of those subdirectories in the processed data logs, you will find multiple output and error files: one for each task/run combination that was processed when the pipeline failed, and, in some cases, files for setup and teardown steps.

The runs are processed in parallel, and the pipeline does not fail until all of the steps of the stage have either passed or failed, so you cannot assume the last run is "guilty". Also, more than one run might have a problem. The quickest way to check what failed is to look at the file called `status.json`. You will see something like `stage terminated with exit code [0, 0, 1, 1]`. In this example, 2 steps failed, and they were the 3rd and 4th steps. If the stage has a setup and teardown (like DCANBOLDProcessing), then this status would tell you that setup and the first run succeeded, the second run failed, and teardown failed. If this `status.json` were found in FMRIVolume, then the 3rd and 4th runs failed (because there is no setup or teardown in FMRIVolume). Just look around at the output and error files available in the directory and it should make sense.

Another way to check which step failed is: type `tail *.err` which will show the last 10 lines of each error file. Each run that succeeded will end with a message to indicate that the stage completed. For example, each successful run in FMRIVolume would have the message, `GenericfMRIVolumeProcessingPipeline.sh - Completed` at the end. Any file that does not have such a message has had an error. Open the file and look for the first error.


### FMRIVolume Could Not Create a Scout File

The most common error in FMRIVolume occurs when a Scout file cannot be created. In the current version, you will find `Too few frames...Exiting`.

We try to use the 17th frame in the file to make the Scout file because the babies have settled a little bit by then. We can use a different frame, but, if there are &lt; 17 frames, the data is not much use. The fix is to remove that file from your `func `directory so that the pipeline will not try to process it. You can restart at FMRIVolume, since no `func `files will have been used before this stage.


### FMRISurface Did Not Find All ROIs

During FMRISurface we attempt to map the subcortical areas. If you ran using ROI_MAP as your subcortical-map-method (the default), the pipeline split the subcorticals and attempted to map each. The pipeline expected to find 19 regions of interest (ROIs). Sometimes an aseg will not have all 19 ROIs. The error log for the run will have the string `ERROR: cifti xml dimensions must be greater than zero`. 

Which subcortical was missing may not matter to you. The message means the run cannot be used as is, so you can decide to eliminate that run. But if you want to debug further, look at the line above that message. It will say something like:


```
    wb_command -cifti-create-dense-timeseries /output/.../files/MNINonLinear/ROIs/task-rest_run-01_working_directory/task-rest_run-01_temp_subject_ROI0008.dtseries.nii -volume sub2atl_vol_masked_ROI0008.nii.gz /output/.../files/MNINonLinear/ROIs/task-rest_run-01_working_directory/sub2atl_vol_label_ROI0008.nii.gz
```


From the message you can find:



* The working directory. Since the job was probably run using Docker, the path to the working directory cannot be used “as is”. Your data will have been mounted to `/output`, so you would substitute the appropriate path for `/output`. Hint: the working directory will always be `files/MNINonLinear/ROIs/&lt;frminame>`. 
* The first ROI for which no data was found. In our example, ROI0008. Since the ROI files are made using `wb_command -volume-all-labels-to-rois`, the ROI numbering starts at 0. That is, ROI0000 is the name used for the 1st ROI. So ROI0008 represents the 9th ROI. 

Go to the working directory (it will not have been removed since there were errors), andl find a file named `labelfile.txt`. The file has 2 lines per ROI, so, for the 9th ROI, you want to look at lines 17 and 18:


```
    17: ACCUMBENS_LEFT
    18: 26 255 165 0 255
```


The first missing ROI was the left accumbens. Its FreeSurfer label was 26 (that is, if you viewed the file with fslview, its “intensity” would be 26). If you have a way to correct the aseg, that is the ROI you need to add.

There might be more missing ROIs; the command died at the first one.


## Other Errors

If your error was not found here, please contact the computing team. We will be happy to help you debug the problem. If you don’t need help, please contact us anyway. We would like to add your error to our document.

