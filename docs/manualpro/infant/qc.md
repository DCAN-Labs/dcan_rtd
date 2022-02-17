# Quality Control for Infant Data


## Post-Processing Quality Assessment from Executive Summary
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx1.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx2.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx3.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx4.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx5.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx6.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx6.1.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx7.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx8.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx9.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx10.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx11.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx12.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx13.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx14.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx15.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx16.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx17.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx18.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx19.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx20.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx21.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx22.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx23.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx24.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx25.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx26.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx27.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx28.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx29.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx30.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx31.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx32.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx33.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx34.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx35.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx36.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx37.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx38.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx39.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx40.png "powerpoint slide")
![powerpoint_slide](../../images/Infant/QC/INFANT_SOP_post-processing_7.23.19.pptx41.png "powerpoint slide")

## Troubleshooting anatomical and functional issues in pipeline output images

**<span style="text-decoration:underline;">Introduction</span>**

Because there are many aspects of infant processing and quality assessment that are new and have yet to be standardized, we occasionally need to perform a deeper quality assessment that requires checking the data in the subject’s processed folder to look at the quality in greater detail than the executive summary may allow. Below are some main “spot checks” to perform if this is the case:

**(1) Atlas registration**

To check how well the anatomical images are registered to the atlas, use fslview or other visualization program to overlay **T1w_restore_brain.nii.gz** (under _sub-****/ses-None/files/MNINonLinear_) and **INFANT_MNI_T1_1mm.nii.gz **(/home/groups/brainmri/infant/TEMPLATES_FOLDERS/&lt;age range>) (it’s easiest to see the quality of registration with the subject brain overlaid on the atlas head). Click around to different areas of the brain and make sure that the 2 images are relatively well-registered, particularly around the edges.

![FuncStruct_registration_example](../../images/Infant/FuncStruct_registration_example.jpeg "FuncStruct_registration_example")


**(2) Functional to structural registration**

To check functional to structural registration, overlay the subject’s BOLD image from one of the runs, eg** task-rest_run-*.nii.gz** (under  _sub-****/ses-None/files/MNINonLinear/Results/task-rest_run-*_) on top of **T2w_restore_brain.2.nii.gz** (under _sub-****/ses-None/files/MNINonLinear_). Change the BOLD image color to see it more easily (eg “Red-yellow” color option in fslview) and decrease opacity to 75% or so in order to see how well it is registered to the anatomical image.

![FuncStruct_registration_HeatMap](../../images/Infant/FuncStruct_registration_HeatMap.jpeg "FuncStruct_registration_HeatMap")

