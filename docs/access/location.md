# DCAN Code and Data Locations at UMN

## Permissions

To ensure the data and code created can be accessed by all, update you bashrc with the following steps:

- Type in terminal: gedit ~/.bashrc
  - This prompts gedit to open your bashrc file
- Set umask to 002

  ![image](images/gedit.png)

- Close the file and type "source ~/.bashrc" info the tpermail to apply the changes

## Code

Code will be saved the the msi in a central location where everyone can access it

**Location**: /panfs/roc/groups/8/faird/shared/code  
        - *Location shortcut*: /home/faird/shared/code

**Folder organization**: The folder “code” will have two directories: internal and external. Each directory will have subdirectories for different types of code (analyses, utilities, etc). Repos (example FRF, fconn anova) will live in each folder. See example below taken from rushmore at ohsu
Current folder structure via tree command:

### /home/faird/shared/code/external/utilities/tree-1.8.0/tree -d -L 3 /home/faird/shared/code/

/home/faird/shared/code/  

```markdown
├── external  
│   ├── analytics  
│   │   └── abcd-heap-feat  
│   ├── GUIs  
│   ├── pipelines  
│   │   └── fmriprep-rodents-test  
│   ├── platforms  
│   │   └── DEAP  
│   ├── src  
│   └── utilities  
│       ├── distribute_readwrite_cifti  
│       ├── mri_conv-master  
│       ├── nhp-brainextraction  
│       ├── pandoc  
│       ├── tree-1.8.0  
│       └── workbench  
└── internal  
    ├── analytics  
    │   ├── DCANCCA  
    │   ├── FRF  
    │   ├── MarginalModelCIFTI  
    │   └── NormativeModeling  
    ├── GUIs  
    │   ├── DEAP  
    │   └── GUI_environments  
    ├── pipelines  
    │   ├── ABCD-BIDS  
    │   ├── DCAN-infant-BIDS  
    │   ├── freesurfer_license  
    │   ├── install_folder  
    │   └── nhp-ABCD-BIDS  
    ├── platforms  
    └── utilities  
        ├── ABCD-BIDS-task-fmri-pipeline  
        ├── abcd_task_prep  
        ├── automated_subset_analysis  
        ├── basic_stats  
        ├── CIFTI  
        ├── cifti_connectivity  
        ├── cifti-matlab  
        ├── cifti_tools  
        ├── cifti_utilities  
        ├── CommunityChiSquaredAnalysis  
        ├── connectotyping  
        ├── dcan  
        ├── Dcm2Bids  
        ├── fconn_matrices_tools  
        ├── fconn_stats  
        ├── figure_maker  
        ├── file-mapper  
        ├── files_handling  
        ├── generic_for_functions  
        ├── gifti  
        ├── graph_metrics  
        ├── GUI_brain_connectivity  
        ├── GUI_environments  
        ├── image_manipulation  
        ├── MachineLearning_SVM  
        ├── Matlab_CIFTI  
        ├── MatlabCompiledRuntimes  
        ├── movement_regressors_power_plots  
        ├── nda-abcd-s3-downloader  
        ├── ParallelPconnGenerator  
        ├── PBSdemo  
        ├── plotting-tools  
        ├── polyneuro_risk_score  
        ├── ReadDir  
        ├── recursive-connectivity  
        ├── sandbox  
        ├── SurfConnectivity  
        ├── tables_handling  
        ├── test_release_connectotyping  
        └── text_manipulation  
 ```

Each repo must be kept under version control and has a developer responsible.  
Stewardship is defined in the following table:  
[INSERT TABLE]  
Steward is responsible for keeping the code updated and making sure folder permissions are not chaged after updating code.  

## Data

To optimize computing resources the MSI offers two types of [storage](https://www.msi.umn.edu/content/storage-allocations): [High Performance Storage](https://www.msi.umn.edu/content/high-performance-storage) and [Second Tier Storage](https://www.msi.umn.edu/content/second-tier-storage). Data in the High Performance Storage is backed up and is accessible from all MSI system. Big data is stored in the Second Tier. Data for each particular project can be found on each PI’s space, depending on who leads each particular project. This table (make a md table describing ) summarizes the existing datasets in the DCAN.

DCAN’s High Performance Storage data is located here:

- **/panfs/roc/groups/8/faird/shared/data**  
- **/panfs/roc/groups/4/miran045/shared/data**  
- **/panfs/roc/groups/4/feczk001/shared/data**  
- **/panfs/roc/groups/4/rando149/shared/data**  

DCAN’s storage can also be accessed from MSI using the following shortcuts:

- **/home/faird/shared/data**  
- **/home/miran045/shared/data**  
- **/home/feczk001/shared/data**  
- **/home/rando149/shared/data**  

Below is the current structure for shared data on each server:  

### /home/feczk001/shared/data

```markdown
├── adhd_subs_transfer  
│   ├── derivatives  
│   │   ├── abcd-hcp-pipeline  
│   │   └── CBRAIN-abcd-hcp-pipeline  
├── BCP  
│   ├── derivatives  
│   │   └── dcan-infant-pipeline  
│   ├── processed  
│   │   └── test5_output  
│   └── sorted  
├── BIDS_rat  
├── HCP  
│   ├── derivatives  
│   │   ├── dcan-abcd-hcp  
│   │   └── dcan-macaque-pipeline  
│   ├── processed  
│   │   ├── ABCD  
│   │   └── Infants  
│   └── sorted  
│       └── NHP_anesthesia_Brambink  
└── manifests  
    ├── BCP  
    └── FezABCD  
    └── experiments  
```

### /home/miran045/shared/data

```markdown
├── abcd  
│   ├── BIDS  
│   ├── fconns  
│   ├── prep_ctype  
│   └── variance_files  
├── GUI_environments_training  
│   └── data  
└── macaque_2yo_anesthesia  
    └── BIDS  
```

### /home/faird/shared/data/

```markdown  
└── BCP_QSIprep
```

Our group has access to 480 TB of Second Tier Storage.  
Requests to save data on primary or secondary storage must be submitted to DCAN leadership. For more information on transferring data between storage locations, visit our data tranfer pages within this Read the Docs page.

## Projects

Specific projects where derived measures are extracted from data (see above) and analyses are conducted can be found in respective projects folders:

- /home/faird/shared/projects
- /home/miran045/shared/projects
- /home/feczk001/shared/projects

Current active prohects are listed below for each subfolder:

**/home/faird/shared/projects**:  

**/home/miran045/shared/projects**:  

- **ADHD_comm_det** Analysis of ADHD data collected at OHSU under Dr. Joel Nigg, includes:
  - **ADHD_CCA** ADHD canonical correlation analysis of template definitions with ???
  - **ADHD_num_nets_palm** ADHD analysis of overlapping networks via PALM
  - **ADHD_templmatch** ADHD template matched datasets
- **FOG_left_pallidus** Examination of freezers/non-freezers of left-pallidus connectivity
- **Gates_infant_toddler_filtering** Analysis of motion filtering for BCP study
- **Polyneuro_risk_score** Polyneuro calculations for ABCD data, specifically EF -- may expand to OHSU collected ADHD as well, hence not in ABCD projects folder
- **visual_inspection_timecourses** -- demonstration of visualizing timecourses using matlab and ABCD data  

**/home/feczk001/shared/projects**:

- **ABCD Projects** related to the ABCD study and include:  
  - **Integrative zones**  parcellated connectivity matrices for ABCD-1 and ABCD-2 are here for the integrative zones  
  - **Integrative zones probability labels** labelfiles for integrative zones at multiple thresholds are located here  
  - **Gordon sets** parcellated connectivity matrices for ABCD-1 and ABCD-2  
  - **Average_surfaces** generated from ABCD-1 and ABCD-2 for functional analyses and data visualization  
  - **Conan_subset_analysis** reliability analyses for ABCD-1 and ABCD-2  
  - **Threshold_template_maps** threshold template connectivity matrices for ABCD-2 and ABCD-2 respectively  
  - **Pconn_demo** demonstration of pconn generation using ABCD data  
  - **Abcd-sync** ABCD DAIRC comparisons to ABCD BIDS
- **ADHD** Projects related to the ADHD study collected at OHSU under Dr. Joel Nigg. Includes the ADHD parcellated connectivity matrices  
- **FEZ_USERS** Private projects for training and development -- not for public use  
- **Macaque_test** Test of the macaque pipeline at UMN  
- **Workflow_demos** Demonstration of the parallel pconn generator  
