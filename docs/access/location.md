# DCAN Code and Data Locations at UMN

## Permissions

To ensure the data and code created can be accessed by all, update you bashrc with the following steps:

- Open your bashrc file with a text editor
  - emacs ~/.bashrc
- Set umask to 0007
- Close the file and type "source ~/.bashrc" info the terminal to apply the changes

## Code

Code will be saved the the msi in a central location where everyone can access it

**Location**: /panfs/roc/groups/8/faird/shared/code  
        - *Location shortcut*: /home/faird/shared/code

**Folder organization**: The folder “code” will have two directories: internal and external. Each directory will have subdirectories for different types of code (analyses, utilities, etc). Repos (example FRF, fconn anova) will live in each folder. See example below taken from rushmore at ohsu
Current folder structure via tree command:

### /home/faird/shared/code/external/utilities/tree-1.8.0/tree -d -L 3 /home/faird/shared/code/

/home/faird/shared/code/  

```markdown
├── dev 
├── external  
│   ├── analytics  
│   │   └── abcd-heap-feat
│   ├── envs  
│   │   └── miniconda3
│   ├── GUIs  
│   ├── pipelines  
│   │   └── ABCD-XCP 
│   │   └── fmriprep-rodents-test
│   │   └── HCPpipelines
│   │   └── nibabies
│   │   └── symri
│   ├── platforms  
│   │   └── DEAP  
│   ├── ROIS
│   │   └── ColeAnticevicNetPartition
│   ├── src  
│   └── utilities  
│       ├── ciftify
│       ├── cifti-matlab
│       ├── circularGraph
│       ├── datalad-nda
│       ├── dcan_regressor
│       ├── distribute_readwrite_cifti
│       ├── fairly-big-processing-workflow
│       ├── freesurfer_license
│       ├── gifti
│       ├── gifti-1.6
│       ├── gramm
│       ├── infomap
│       ├── MATLAB_Runtime_R2017a
│       ├── MATLAB_Runtime_R2019a
│       ├── MATLAB_Runtime_R2019a_update9
│       ├── MATLAB_Runtime_R2021a
│       ├── mri_conv-master
│       ├── MSCcodebase-master
│       ├── nda_manifest
│       ├── nda_rds_files
│       ├── nda-tools
│       ├── nhp-brainextraction  
│       ├── pandoc  
│       ├── tree-1.8.0  
│       ├── v100pytorch
│       ├── workbench
│       └── xmltree-2.0  
└── internal  
│    ├── analytics  
│    │   ├── compare_matrices_copy_to_merge_from
│    │   ├── compare_matrices_to_assign_networks    
│    │   ├── DCANCCA  
│    │   ├── FRF  
│    │   ├── MarginalModelCIFTI  
│    │   ├── NormativeModeling
│    │   └── PEAS  
│    ├── GUIs  
│    │   ├── DEAP  
│    │   └── GUI_brain_connectivity  
│    ├── HPC_processing
│    │   ├── hBCD_BCP_QSIprep
│    │   ├── S1042_TMS_Tics
│    │   ├── S1053_TMS_Fear
│    │   └── seed_map_wrapper
│    ├── nnUNet
│    │   └── slurm_scripts
│    ├── pipelines  
│    │   ├── ABCD-BIDS  
│    │   ├── abcd-hcp-pipeline
│    │   ├── bidsnet
│    │   ├── CABINET
│    │   ├── DCAN-infant-BIDS  
│    │   ├── dcan-infant-pipeline
│    │   ├── dcan-nn-unet
│    │   ├── freesurfer_license
│    │   ├── infant-abcd-bids-pipeline
│    │   ├── install_folder  
│    │   ├── nhp-ABCD-BIDS
│    │   ├── nibabies
│    │   └── pipeline-subission  
│    ├── platforms  
│    └── utilities  
│        ├── ABCD-BIDS-task-fmri-pipeline  
│        ├── abcd-hcp-pipeline_audit
│        ├── automated_subset_analysis  
│        ├── basic_stats
│        ├── biceps
│        ├── BIDS-FM
│        ├── CIFTI  
│        ├── cifti_connectivity
│        ├── CIFTIScalarAnalysis  
│        ├── cifti_tools  
│        ├── cifti_utilities 
│        ├── combine_bids_sessions
│        ├── CommunityChiSquaredAnalysis
│        ├── community_detection
│        ├── connectotyping  
│        ├── dcan_bold_processing  
│        ├── Dcm2Bids  
│        ├── deface
│        ├── fconn_matrices_tools  
│        ├── fconn_stats  
│        ├── figure_maker  
│        ├── file-mapper  
│        ├── files_handling  
│        ├── generic_for_functions  
│        ├── hcp-pipeline_audit 
│        ├── image_manipulation
│        ├── infomap_community_detection
│        ├── intendedforgui
│        ├── JSONS-Examples
│        ├── MachineLearning_SVM 
│        ├── mahalanobis_outlier_identifier
│        ├── Matlab_CIFTI  
│        ├── MatlabCompiledRuntimes 
│        ├── MergeTimeSeires
│        ├── movement_regressors_power_plots  
│        ├── nda-abcd-s3-downloader
│        ├── nda-bids-upload-prepare
│        ├── nibabies_submission
│        ├── NKI-Rockland_raw_download
│        ├── NORDIC
│        ├── outlier-sensoring
│        ├── output
│        ├── ParallelPconnGenerator  
│        ├── PBSdemo  
│        ├── pconn_rows_to_pscalar
│        ├── pipeline_wrappers
│        ├── plotting-tools  
│        ├── polyneuro_risk_score  
│        ├── ReadDir  
│        ├── read_volumes
│        ├── recursive-connectivity  
│        ├── reformat_motion_numbers
│        ├── save
│        ├── seed_map_wrapper
│        ├── simnibs_cifti_tools
│        ├── singularity
│        ├── slurm_pipeline_wrappers
│        ├── SurfConnectivity  
│        ├── tables_handling  
│        ├── test_release_connectotyping  
│        ├── text_manipulation
│        ├── VARS
│        └── Zscore_dconn
└── stable
     └── utilities
         └── BWAS_PNRS_package
         
```

Each repo must be kept under version control and has a developer responsible.  
Stewardship is defined in the following table:  
*NOTE: Steward is responsible for keeping the code updated and making sure folder permissions are not chaged after updating code.*

| Tool | Description | Steward\_name | Steward\_X500 | Language  | Source | Type   | path in the msi | Path to git\*b (New code should be on github) | Additional documentation | Comment |
| - | - | - | - | - | - | - | - | - | - | - |
| compare\_matrices\_copy\_to\_merge\_from  | Compare matrices copy that needs to be merged. | Robert | hermosir | Matlab | internal | analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/compare\_matrices\_copy\_to\_merge\_from |  | To be removed after merge |
| compare\_matrices\_to\_assign\_networks | Compare matrices development repo. | Robert | hermosir | Matlab | internal | analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/compare\_matrices\_to\_assign\_networks  | [https://gitlab.com/Fair\_lab/compare\_matrices\_to\_assign\_networks](https://gitlab.com/Fair_lab/compare_matrices_to_assign_networks) | | |
| DCANCCA | Perform Sparse canonical correlation analysis with multiple imputation and cross validation options | Fez | feczk001 | R | internal | analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/DCANCCA | [https://gitlab.com/Fair\_lab/dcancca/](https://gitlab.com/Fair_lab/dcancca/) | | To be removed after merge |
| FRF | Hybrid approach that combines functional data analysis, random forests, and community detection for identifying subtypes tied to an outcome | Fez | feczk001 | Matlab | internal |analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/FRF | [https://github.com/DCAN-Labs/functional-random-forest](https://github.com/DCAN-Labs/functional-random-forest) | [https://github.com/DCAN-Labs/functional-random-forest/blob/master/README.md](https://github.com/DCAN-Labs/functional-random-forest/blob/master/README.md) | Needs some updates -- was considering refactoring to R but abandoned to due lack of cycles |
| MarginalModelCIFTI | Marginal model approach for brain-wide assocations, works on all formats including tabulated data | Fez | feczk001 | R | internal | analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/MarginalModelCIFTI | [https://github.com/DCAN-Labs/MarginalModelCIFTI](https://github.com/DCAN-Labs/MarginalModelCIFTI) | [https://github.com/DCAN-Labs/MarginalModelCIFTI/README.md](https://github.com/DCAN-Labs/MarginalModelCIFTI) | Needs to be renamed to SEND |
| NormativeModeling | Normative Modelling for identifying subtypes | Fez | feczk001 | TBD | internal |analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/NormativeModeling |  | | may be abandoned for now -- was intened for normative modeling approaches |
| PEAS | Extracting subtypes from polyneuro subtypes | Fez | feczk001 | Matlab/R/bash | internal | analytics | /panfs/roc/groups/8/faird/shared/code/internal/analytics/PEAS | [https://gitlab.com/Fair\_lab/Polyneuro-Extraction-of-ARMS-Subtypes](https://gitlab.com/Fair_lab/Polyneuro-Extraction-of-ARMS-Subtypes) | | needs to be deleted after merge -- should be renamed to SPEAR |
| DEAP | Data analysis and exploration portal | Fez | feczk001 | CSS/javascript/R     | internal | GUIs | /panfs/roc/groups/8/faird/shared/code/internal/GUIs/DEAP |  | | |
| GUI\_brain\_connectivity | GUI to make graph theory on connectivity matrices | Oscar | miran045 | Matlab | internal | GUIs | /panfs/roc/groups/8/faird/shared/code/internal/GUIs/GUI\_brain\_connectivity | [https://gitlab.com/ascario/GUI\_brain\_connectivity](https://gitlab.com/ascario/GUI_brain_connectivity) | | Done ~2012. It is not cifti compatible |
| hBCD\_BCP\_QSIprep | Used to produce QSIPrep outputs for the hBCD study with the baby connectome project (BCP) data. Folder holds the scripts that Tim used to perform the processing / analyses. | Tim H | hendr522 | bash | internal | HPC\_processing | /panfs/roc/groups/8/faird/shared/code/internal/HPC\_processing/hBCD\_BCP\_QSIprep | | | |
| ABCD-BIDS | human adult/child pipeline | Fez/Earl/Anders | feczk001 | bash/matlab/python | internal | pipelines | /panfs/roc/groups/8/faird/shared/code/internal/pipelines/DCAN-infant-BIDS | [https://github.com/DCAN-Labs/abcd-hcp-pipeline](https://github.com/DCAN-Labs/abcd-hcp-pipeline) | | |
| DCAN-infant-BIDS | human infant pipeline | Kathy/Luci | ksnider/lmoore | bash/matlab/python | internal | pipelines | | [https://github.com/DCAN-Labs/infant-abcd-bids-pipeline](https://github.com/DCAN-Labs/infant-abcd-bids-pipeline) | | |
| freesurfer\_license | this is a freesurfer\_license.txt file, not sure if it needs a steward, and should probably be moved to external | Fez/Kathy                          | feczk001/ksnider | NA | internal | pipelines | /panfs/roc/groups/8/faird/shared/code/internal/pipelines/freesurfer\_license | | | |
| install\_folder | set of scripts for installing pipelines on MSI | Fez | feczk001 | bash | internal | pipelines | /panfs/roc/groups/8/faird/shared/code/internal/pipelines/install\_folder | | | |
| nhp-ABCD-BIDS | macaque pipeline | Thomas/Anders | tmadison/perr0372 | bash/matlab/python | internal | pipelines | /panfs/roc/groups/8/faird/shared/code/internal/pipelines/nhp-ABCD-BIDS | [https://github.com/DCAN-Labs/nhp-abcd-bids-pipeline](https://github.com/DCAN-Labs/nhp-abcd-bids-pipeline) | | |
| abcd\_task\_prep | Not sure if currently used. Give Greg permission to folder. | Greg | gconan | ? | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/abcd\_task\_prep | | | |
| ABCD-BIDS-task-fmri-pipeline | ABCD-BIDS task pipeline using FEAT GLM | Anthony Juliano/Greg | gconan | bash/python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/ABCD-BIDS-task-fmri-pipeline | [https://github.com/DCAN-Labs/ABCD-BIDS-task-fmri-pipeline](https://github.com/DCAN-Labs/ABCD-BIDS-task-fmri-pipeline) | | |
| automated\_subset\_analysis | subset reliability analysis for ARMS -- works with everything though | Greg | gconan | python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/automated\_subset\_analysis              | [https://gitlab.com/Fair\_lab/automated-subset-analysis](http://gitlab.com/Fair_lab/automated-subset-analysis) | | |
| basic\_stats | report basic stats. Used by several other functions | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/basic\_stats | [https://gitlab.com/Fair\_lab/basic\_stats.git](https://gitlab.com/Fair_lab/basic_stats.git) | | |
| biceps | Brain Imaging Connectivity Extraction Program Solution: Tool to calculate connectivity matrices out of bids derivatives | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/biceps | git@github.com:DCAN-Labs/biceps.git | [https://gui-environments-documentation.readthedocs.io/en/latest/GUI\_environments/](https://gui-environments-documentation.readthedocs.io/en/latest/GUI_environments/) | GUI\_environments rebranded |
| CIFTI | external repo, contains cifti\_open | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/CIFTI | [https://github.com/OHBA-analysis/CIFTI.git](https://github.com/OHBA-analysis/CIFTI.git) | | Oscar downloaded the code. It should libe in external, needs to be conciliated with the other versions of CIFTIS |
| cifti\_connectivity | Creates connectivity matrices from time series | Greg/Robert | hermosir | Matlab/python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/cifti\_connectivity | [https://github.com/DCAN-Labs/cifti-connectivity](https://github.com/DCAN-Labs/cifti-connectivity) | | |
| cifti\_tools | code from HCP-WashU with cifti tools. | Oscar | miran045             | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/cifti\_tools | | | |
| cifti\_utilities | A collection of cifti utilities from a variety of users | Fez/Anders/Kathy/<br>Oscar/Robert/Greg | feczk001 | bash/matlab/python/R | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/cifti\_utilities | | | |
| CIFTIScalarAnalysis | collection of utilities for working with CIFTIs -- used for prepping data for PALM | Feczko | feczk001 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/CIFTIScalarAnalysis | [https://github.com/DCAN-Labs/CIFTIScalarAnalysis/](https://github.com/DCAN-Labs/CIFTIScalarAnalysis/) | | |
| CommunityChiSquaredAnalysis | chi-squared enrichment analysis written in Matlab | Fez | feczk001 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/CommunityChiSquaredAnalysis | [https://github.com/DCAN-Labs/CommunityChiSquaredAnalysis](https://github.com/DCAN-Labs/CommunityChiSquaredAnalysis) | | |
| connectotyping | connectotyping: model based connectivity matrices | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/connectotyping | [https://gitlab.com/ascario/connectotyping](https://gitlab.com/ascario/connectotyping) | | Needs to be conciliated with Paul's version |
| Dcm2Bids | [Dcm2Bids reorganises NIfTI files from dcm2niix into the Brain Imaging Data Structure (BIDS).](https://github.com/rordenlab/dcm2niix) | Anders | perr0372 | python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/Dcm2Bids | [https://github.com/DCAN-Labs/Dcm2Bids/](https://github.com/DCAN-Labs/Dcm2Bids/) | | |
| fconn\_matrices\_tools | tools to calculate means and distributions of fconn matrices. Also contains parcellation schemas | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/fconn\_matrices\_tools | [https://gitlab.com/Fair\_lab/fconn\_matrices\_tools.git](https://gitlab.com/Fair_lab/fconn_matrices_tools.git) | | |
| fconn\_stats | tools to calculate differences in connectivity among groups, PLSR, among other things | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/fconn\_stats                             | [https://gitlab.com/Fair\_lab/fconn\_stats.git](https://gitlab.com/Fair_lab/fconn_stats.git) | [https://fconn-anova.readthedocs.io/en/latest/](https://fconn-anova.readthedocs.io/en/latest/) <br> [https://fconn-regression.readthedocs.io/en/latest/](https://fconn-regression.readthedocs.io/en/latest/) | |
| figure\_maker | A utility that creates png from a cifti data file. | Robert/Greg | hermosir/gconan | Bash/python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/figure\_maker | [https://gitlab.com/Fair\_lab/figure-maker](https://gitlab.com/Fair_lab/figure-maker) | | |
| file-mapper | An easy way to copy/move/symlink files from one directory to another all-in-one. | Kathy | ksnider | python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/file-mapper | [https://github.com/DCAN-Labs/file-mapper/](https://github.com/DCAN-Labs/file-mapper/) | |
| files\_handling | functions to get path to files and folders | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/files\_handling | [https://gitlab.com/ascario/files\_handling.git](https://gitlab.com/ascario/files_handling.git) | | |
| generic\_for\_functions | small functions used by other functions.<br>\- encapsulate text with quotes If space<br>\- make random text for temp filenames<br>\- format text in figures to have the same resolution | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/generic\_for\_functions | [https://gitlab.com/Fair\_lab/generic\_for\_functions](https://gitlab.com/Fair_lab/generic_for_functions) | | |
| image\_manipulation | tools to make a mosaic based on individual pictures | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/image\_manipulation | [https://gitlab.com/Fair\_lab/image\_manipulation](https://gitlab.com/Fair_lab/image_manipulation) | Made to combine photos taken with a microscope |
| infomap\_community\_detection | Revisit who should be steward in 6 months. Cristian working through streamlining this. | Robert / Cristian | hermosir / moral453  | Multiple | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/infomap\_community\_detection | | | |
| MachineLearning\_SVM | Classifier using Support Vector Machine  used in the manuscript "Heritability of the Human Connectome" | Oscar                              | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/MachineLearning\_SVM | [https://github.com/DCAN-Labs/MachineLearning\_SVM](https://github.com/DCAN-Labs/MachineLearning_SVM) | | |
| Matlab\_CIFTI | Contains ciftiopen, ciftisave | Oscar | miran045 | Matlab | internal | utilities  | /panfs/roc/groups/8/faird/shared/code/internal/utilities/Matlab\_CIFTI | | | Not in version control. Should be external and needs to be conciliated with the other versions of cifti open |
| MatlabCompiledRuntimes | collected and stored needed to run matlab compiled code | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/MatlabCompiledRuntimes | | | |
| movement\_regressors\_power\_plots | Tools to viualize power spectra of motion numbers | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/movement\_regressors\_power\_plots | [https://github.com/DCAN-Labs/movement\_regressors\_power\_plots.git](https://github.com/DCAN-Labs/movement_regressors_power_plots.git) | | |
| nda-abcd-s3-downloader | ABCD downloader tool to access S3 directly | Anders | perr0372 | python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/nda-abcd-s3-downloader | [https://github.com/ABCD-STUDY/nda-abcd-s3-downloader](https://github.com/ABCD-STUDY/nda-abcd-s3-downloader) | | |
| ParallelPconnGenerator | bash program for parallel pconn and ptseries generation -- wrapper for cifti\_connectivity | Fez | feczk001 | bash | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/ParallelPconnGenerator | [https://gitlab.com/Fair\_lab/parallelpconngenerator](https://gitlab.com/Fair_lab/parallelpconngenerator) | | To be removed after merge |
| paths\_oscar\_code.md | remove | | | | | | | | | Removed on May 5, 2021 |
| PBSdemo | demo for how to use the decommissioned PBS grid | Fez | feczk001 | bash | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/PBSdemo | | | can be discontinued |
| pconn\_rows\_to\_pscalar | Summarizes a pconn the sum of the weights of each row, to visualize as a scalar | Robert | hermosir | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/pconn\_rows\_to\_pscalar                | | | |
| plotting-tools | Tools to make histograms, boxplots, to visualize connectivity matrices, etc | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/plotting-tools                           | [https://gitlab.com/ascario/plotting-tools](https://gitlab.com/ascario/plotting-tools)  |  | Includes showM  |
| polyneuro\_risk\_score | Tools to calculate BWAS/PNRS | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/polyneuro\_risk\_score | [https://gitlab.com/Fair\_lab/polyneuro\_risk\_score.git](https://gitlab.com/Fair_lab/polyneuro_risk_score.git) | [https://polyneuro-risk-score.readthedocs.io/en/latest/](https://polyneuro-risk-score.readthedocs.io/en/latest/) | |
| ReadDir | super fast tool for listing files written in Perl | Fez | feczk001 | Perl | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/ReadDir | [https://gitlab.com/Fair\_lab/readdir](https://gitlab.com/Fair_lab/readdir) | | |
| recursive-connectivity | Tools to calculate connectivity matrices using recursive estimation | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/recursive-connectivity | [https://gitlab.com/Fair\_lab/recursive-connectivity.git](https://gitlab.com/Fair_lab/recursive-connectivity.git) | | WIP |
| seed\_map\_wrapper | Correlates whole-brain connectivity to seed. | Robert/Greg | hermosir/gconan | matlab/bash/python | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/seed\_map\_wrapper | [https://gitlab.com/Fair\_lab/Cifti\_conn\_matrix\_to\_corr\_dt\_pt](https://gitlab.com/Fair_lab/Cifti_conn_matrix_to_corr_dt_pt)       | [https://gitlab.com/randolpa/seed-map-parcellation-wrapper-sop](https://gitlab.com/randolpa/seed-map-parcellation-wrapper-sop) | Anita has been working on documentation of this code. |
| singularity | Caches for compiling singularity builds. Can help singularity build faster. | Not assigned | Not assigned | NA | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/singularity | | | |
| SurfConnectivity | collection of compiled utilities for performing cluster detection in other languages like R | Fez | feczk001 | Matlab                       | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/SurfConnectivity | [https://github.com/DCAN-Labs/SurfConnectivity](https://github.com/DCAN-Labs/SurfConnectivity) |  |  |
| tables\_handling | Tools to add fileds, rename headers, etc | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/tables\_handling | [https://gitlab.com/Fair\_lab/tables\_handling.git](https://gitlab.com/Fair_lab/tables_handling.git) | | |
| test\_release\_connectotyping | old version of connectotyping | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/test\_release\_connectotyping | | | Not in version control. Conciliate with current branch and Paul's version |
| text\_manipulation | Several functions to import and handle test in Matlab. Includes importData | Oscar | miran045 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/text\_manipulation | [https://gitlab.com/Fair\_lab/text\_manipulation](https://gitlab.com/Fair_lab/text_manipulation) | | |
| VARS | Mulitple shaded line plot visualizations controlled via command line interface  | Fez | feczk001 | Matlab | internal | utilities | /panfs/roc/groups/8/faird/shared/code/internal/utilities/VARS | [https://gitlab.com/Fair\_lab/vars](https://gitlab.com/Fair_lab/vars) | | to be removed after merg |
| wb\_command.txt | remove | | | | | | | | | Removed on May 5, 2021 |
| abcd-heap-feat | outdated version that was going to be used to do a group activation maps | NA | NA | NA | external | analytics | /panfs/roc/groups/8/faird/shared/code/external/analytics/abcd-heap-feat | | | |
| fmriprep-rodents-test | rodent minimal preprocessing pipeline | Thomas | tmadison | Python | external | pipelines | /panfs/roc/groups/8/faird/shared/code/external/pipelines/fmriprep-rodents-test | [https://github.com/poldracklab/fmriprep-rodents](https://github.com/poldracklab/fmriprep-rodents) | | |
| DEAP | ? | Fez | feczk001 | ? | external | platforms | /panfs/roc/groups/8/faird/shared/code/external/platforms/DEAP | | | |
| tree-1.8.0.tar | remove | | | | | | | | | |
| cifti-matlab | function to read gifti files | Oscar | miran045 | Matlab | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/cifti-matlab | [https://github.com/Washington-University/cifti-matlab.git](https://github.com/Washington-University/cifti-matlab.git) | | |
| distribute\_readwrite\_cifti | remove | | | | | | | | | Removed on May 5, 2021 |
| gifti | function to read gifti files | Oscar | miran045 | Matlab | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/gifti | [https://github.com/gllmflndn/gifti.git](https://github.com/gllmflndn/gifti.git) | | Old version to read giftis |
| gifti-1.6 | read giftis and ciftis, utilities we have call 1.6 | Oscar | miran045 | Matlab | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/gifti-1.6 | | | |
| gramm | Data visualization toolbox for matlab - grammatical lang like R | Fez | feczk001  | Matlab | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/gramm | | | |
| infomap | community detection. | Robert | hermosir | C | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/infomap | | | |
| MATLAB\_Runtime\_R2019a\_Update\_9\_glnxa64.zip | remove | | | | | | | | | |
| mri\_conv-master | MRI File Manager (view and export ParaVision data to other formats) | Thomas | tmadison | Java | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/mri\_conv-master | [https://github.com/populse/mri\_conv](https://github.com/populse/mri_conv) | | |
| MSCcodebase-master | A repository from the Midnight scan club that contains unique cifti processing utilies and example cifties | Robert | hermosir | Matlab and other cifti files | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/MSCcodebase-master | [https://github.com/MidnightScanClub/MSCcodebase](https://github.com/MidnightScanClub/MSCcodebase) | |
| nda\_rds\_files | To get tabulated data into a coordinated format | Fez | feczk001 | NA | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/nda\_rds\_files | | | |
| nhp-brainextraction | UNet brain extraction for non-human primates | Thomas | tmadison | Python | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/nhp-brainextraction | [https://github.com/HumanBrainED/NHP-BrainExtraction](https://github.com/HumanBrainED/NHP-BrainExtraction) | | |
| pandoc | convert files from one markup format into another | Fez | feczk001 | MD | external | utilities                                                                 | /panfs/roc/groups/8/faird/shared/code/external/utilities/pandoc | | | |
| tree-1.8.0 | useful to display, in a terminal, directory contents, including directories, files, links. | Fez | feczk001 | ? | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/tree-1.8.0 | | | |
| workbench | Connectome Workbench (alternative installation to MSI's 'workbench' module) | ? | ? | NA | external | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/workbench | | | |
| xmltree-2.0 | necessary for reading giftis | Robert | hermosir | ? | external      | utilities | /panfs/roc/groups/8/faird/shared/code/external/utilities/xmltree-2.0 | | | |
| BrainSegNet3D | This is a general purpose 3D image segmentation architecture using torchio - a Python library for efficient loading, preprocessing, augmentation and patch-based sampling of 3D medical images in deep learning. | Anders/Paul | Jupyter Notebook | internal | deep-learning | | [https://github.com/DCAN-Labs/BrainSegNet3D](https://github.com/DCAN-Labs/BrainSegNet3D) | | |
| abcd-nn-unet | Utility programs created for using nn-UNet for infant brain segmentation. | Paul | reine097 | Python | internal | deep-learning | | [https://github.com/DCAN-Labs/abcd-nn-unet](https://github.com/DCAN-Labs/abcd-nn-unet) | | [Also see https://github.com/MIC-DKFZ/nnUNet](https://github.com/MIC-DKFZ/nnUNet) |
| Container, Biceps@Singularity | singularity container with a standalone version of Biceps | Oscar / Cristian | miran045/moral453 | Singularity / Matlab | internal      | utilities | /panfs/roc/groups/4/miran045/moral453/container\_biceps | | | |

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
├── ABCD
├── ABCD_copy
├── ABCD_sym_for_CuBIDS
├── abcd-sync
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
├── BCP_MSIprocessed_anat
├── BIDS_rat  
├── computerized_loes_scoring
├── datalad
├── HBN
├── HCP-D  
│   ├── derivatives  
│   │   ├── dcan-abcd-hcp  
│   │   └── dcan-macaque-pipeline  
│   ├── processed  
│   │   ├── ABCD  
│   │   └── Infants  
│   └── sorted  
│       └── NHP_anesthesia_Brambink  
├── HNU
├── manifests  
    ├── BCP  
    └── FezABCD  
    └── experiments  
├── MATAAR_subjects
├── nnUNet
├──S1058_3T_adult
└── test
```

### /home/miran045/shared/data

```markdown
├── abcd  
│   ├── BIDS  
│   ├── fconns  
│   ├── prep_ctype  
│   └── variance_files  
├── abcd_nda_retrieved_march_2021
├── ABIDE
├── ADHD
├── BCP
├── essa_7T
├── GUI_environments_training  
│   └── data  
├── macaque_2yo_anesthesia  
│   └── BIDS
├── MSC_to_DCAN
├── S1058
├── UMich
├── washu_me_baby
└── zimmerman_10p5T_macaque_test
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
