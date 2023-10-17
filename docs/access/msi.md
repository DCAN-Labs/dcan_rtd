# The Minnesota Supercomputing Institute

*The [Minnesota Supercomputing Institute](https://www.msi.umn.edu/) (MSI) provides the software, hardware, storage and experts to support research projects in all research areas.*

## Registering for Access

### UMN Employees

[Request an MSI account](https://www.msi.umn.edu/access) and your account can be created from your UMN InternetID (formerly called x500).

### Non-UMN Employees

In order to request an MSI account as a non-UMN employee, a Person of Interest (POI) account must first be created. The requester needs written approval from Dr. Damien Fair or another DCAN Leadership team member. 

Email [DCAN Labs](https://innovation.umn.edu/developmental-cognition-and-neuroimaging-lab/contact-us/) with "POI Account Request" in as your subject to initiate the POI account creation process.

## Gaining Access

### Establish VPN

To remotely log into MSI you need to establish a VPN connection. Detailed instructions can be found on [HST/AHC: VPN and Remote Desktop Setup](https://it.umn.edu/services-technologies/how-tos/hstahc-vpn-remote-desktop-setup) for Windows, OS X, and Linux.

NOTE: If you already have VPN on your computer for another institution, you will need to complete the following steps:

1. Type "tc-vpn-1.umn.edu" in the box
1. Choose "anyconnect-UofMvpnfull" from the group
1. Enter your username and password

*This installs required setups for VPN, after which you will have a dropdown with UMN choices and you can use "split tunnel" moving forward.*

*If you receive an error message the first time, simply re-open Cisco.*

### Permissions

To ensure the data and code created can be accessed by all, update your bashrc with the following steps (this only needs to be done the first time you access MSI). See here for some info on what a "[bashrc](https://www.journaldev.com/41479/bashrc-file-in-linux)" is.

1.  Open your bashrc file with a text editor, e.g. `emacs ~/.bashrc`.
1.  Set `umask` to `0007`. The `umask` is the default permission (self, group, like `faird`, and all users can be given read, write, and execute access) applied to the files you create. `0007` gives read, write, and execute access to you and all group members, but no one else (this could be anyone in the university). See [here](https://wintelguy.com/umask-calc.pl) for details.
1.  Close the file and type `source ~/.bashrc` into the terminal to apply the changes.
1.  Your bashrc is loaded each time you log in, so you only need to `source` it when you edit it mid-session.

## Structure of High Performance Computer (HPC) Systems  

   - To learn more about the structure of the HPC system, visit the [MSI website](https://www.msi.umn.edu/tutorials) for a list of tutorials.  
   - **Launch** 
	   - To launch a GUI desktop-like interface, 
   		visit [NX](https://nx.msi.umn.edu/nxwebplayer) or [NICE](https://nice.msi.umn.edu) and login with your UMN credentials.  
		- MSI can also be accesed through any regular terminal, but you must first log in to a login node: `ssh -Y <user>@login.msi.umn.edu`
		- A login node can be used to browse, view files, etc.
   - **Using clusters**: To perform more advanced tasks, log in to one of MSI's clusters, like [Mesabi](https://www.msi.umn.edu/content/mesabi) or [Mangi](https://www.msi.umn.edu/mangi).
      - From a login node: `ssh -Y <user>@mesabi` or `mangi`.
   - Request resources for interactive computing, for performing simple analyses. For batch processing of many independent jobs (i.e. one job per ABCD session), see the section below.
   **By default, you should request an interactive node**. In some cases (i.e. high priority projects) you might request access to the **dcan** node.
   	- **On Mesabi/Mangi** (see [here](https://www.msi.umn.edu/content/interactive-queue-use-srun) for more detail):
	       - `srun -N 1 --ntasks-per-node=4  --mem-per-cpu=4gb -t 4:00:00 -p interactive --x11 --pty bash`
	        - `-N` is the **number of nodes**, which can have multiple cores/CPUs. Usually, you only need one.
	        - `--ntasks-per-node` is the **number of CPUs**.
	        - To **change memory**, change the argument of the flag `--mem-per-cpu`. Total memory is `mem-per-cpu` times `ntasks-per-node`
	        - To **change time**, change the argument of the flag `-t`. Be sure to specify time completely so you don't end up requesting 4 minutes instead of 4 hours.
      	- **Using the dcan node**. Reserve this node for high priority/high RAM/CPU power demands
        	- `srun -N 1 --cpus-per-task=4 --mem-per-cpu=4gb -t 4:00:00 --x11 -p dcan --pty bash`

   - [Load the module you need](https://www.msi.umn.edu/support/faq/what-module). For example, if you want to run Matlab, just type in terminal `module load matlab`. 
	   - Other common modules include: `fsl`,  `R`, `python2` or `python3`, and HCP `workbench`.
	   - Typing e.g. `module avail R` will show you all the versions available to load, in case versioning matters for your application.

## Data
To optimize computing resources the MSI offers two types of [storage](https://www.msi.umn.edu/content/storage-allocations): 

- [High Performance Storage](https://www.msi.umn.edu/content/high-performance-storage): Data in the High Performance Storage is backed up and is accessible from all MSI systems.
- [Second Tier Storage](https://www.msi.umn.edu/content/second-tier-storage):  Big and archival data is stored in the Second Tier. Data for each particular project can be found on each PI's space, depending on who leads each particular project.

Storage locations should be determined in conversation with one or more DCAN Labs PI, and may change as space needs change. 

## Submitting Jobs

For non-interactive jobs, use [slurm](https://www.msi.umn.edu/content/job-submission-and-scheduling-slurm) for job submissions. 

In short, slurm allows a user to submit a script to be executed, not on the login/interactive node the user is on, but on MSI's various clusters, which are divided into *partitions* with different specifications. 
This [link](https://www.msi.umn.edu/partitions) points to a table that shows the memory and time capacity of each partition for non-interactive jobs. Choosing a partition your job doesn't fit on will cause it not to be run.

There are two main ways to submit a script to slurm.

1. A script can have a complete `#SBATCH` header as described in the link above. However, a job will submit with some default - very low - values, so if you don't specify a time limit, for example, your job will be given only 5 minutes to execute. Submitting these jobs to slurm can be as simple as `sbatch file.sh`.
2. The same `#SBATCH` header options can be given as options to `sbatch`, e.g. `sbatch --time=12:00:00 file.sh`, which can be useful when parameters vary by job, or when setting job names with `-J`, since command line arguments cannot be passed to `#SBATCH` parameters, as they are Bash comments and therefore invisible to the script. 

Scripts submitted to slurm must include any `module` calls necessary.

### Parameters

The main parameters are number of cores: `--ntasks-per-node`; memory (`--memory` or `--mem-per-cpu`), and time (`--time`). It is also sometimes necessary to specify amount of "scratch space" in temporary storage on `/tmp` with `--tmp`. A complete list of options can be found [here](https://slurm.schedmd.com/sbatch.html).

It is important to specify both enough resources for your job, but only just enough. Larger jobs take longer to queue, and smaller jobs can be fit between larger jobs. We recommend testing a handful of jobs to establish parameters as necessary - it can be quite frustrating when a job fails at 36 hours with only an hour left of processing!

Your jobs will be given a numeric ID and you can view all your jobs with `squeue -u <user>` or `squeue --me`. `squeue` alone will give you all jobs submitted to MSI across the university!

You can see how long a job actually took with `seff <ID>`

	Job ID: 10000000
	Cluster: mesabi
	User/Group: park2589/dorfmank
	State: COMPLETED (exit code 0)
	Cores: 1
	CPU Utilized: 00:03:12
	CPU Efficiency: 87.67% of 00:03:39 core-walltime
	Job Wall-clock time: 00:03:39
	Memory Utilized: 289.38 MB
	Memory Efficiency: 14.47% of 1.95 GB

This shows us that 4 minutes was probably a good estimate for this job (although it would have to be contextualized among all the jobs with similar inputs), but 2 GB was probably more than necessary. 

This example job is very small - I wouldn't bother with requesting e.g. 0.5 or 2 GB, but the difference between 24 and 36 hours or 6 and 24 GB memory can definitely influence how long your job takes to start on slurm. 


### Accounts

Each PI has their own allocation on MSI. Damien Fair: `faird`; Eric Feczko `feczk001`; Oscar Miranda-Dominguez: `miran045`; Steve Nelson: `??`; Anita Randolph: `rando149`. These allocations have storage *and* grid time allocated to them. As one account is more active, it becomes deprioritized relative to all other accounts on MSI.

You can see your priority ("FairShare") on each account with `sshare -U <user>` (note the capital `-U`). Higher numbers are better.

If you have permission to use a given PI's account for a given project, you can choose the account with the highest FairShare to get your jobs running sooner and avoid slamming those accounts with an already low FairShare.

### Canceling jobs

Jobs can be canceled with the command `scancel <ID>` or all your jobs with `scancel -u <user>`.


## Delays and Problems

If you experience delays or problems accessing the MSI or a particular node, the reason could be that the MSI might be non-fully operational at that time. The first Wednesday of each month the system is down for maintenance. Use the following links to check the MSI system and node status at any time:

- [MSI System status](https://status.msi.umn.edu/)
- [MSI node status](https://umgcdownload.msi.umn.edu/website/slurmnodes/index.html)

### Reporting Errors

If you are experiencing errors/issues, contact the following people:

- General usage or slurm issues: MSI help desk (`help@msi.umn.edu`)
- Parallelization or code running issues: Tim Hendrickson (`hendr522@umn.edu`)
- Pipeline issues:
  - Infant pipeline: Luci Moore (`lmoore@umn.edu`)
  - Human pipeline: Anders Perrone (`perr0372@umn.edu`)
  - Macaque pipeline: Thomas Madison (`madisoth@ohsu.edu`)
  - Rodent pipeline: Thomas Madison (`madisoth@ohsu.edu`)
  
