# ABCD Study

The Adolescent Beahvior and Cognitive Development (ABCD) neuroimaging dataset is formatted into the [Brain Imaging Data Structure (BIDS) standard](https://bids-specification.readthedocs.io/en/stable/) and processed through the [abcd-hcp-pipeline](https://hub.docker.com/r/dcanumn/abcd-hcp-pipeline). The BIDS data, pipeline derivatives, and associated software are all part of the ABCD-BIDS Community Collection (Collection 3165). A detailed description of this dataset and image processing pipeline can be found at the [ABCC readthedocs](https://collection3165.readthedocs.io/en/stable/).

Manual processing of ABCD neuroimaging data for the ABCC involves 4 steps:

## 1. Downloading DICOMs and BIDS Conversion
### abcd-dicom2bids [https://github.com/ABCD-STUDY/abcd-dicom2bids](https://github.com/ABCD-STUDY/abcd-dicom2bids)

This tool pulls DICOMs and E-Prime files from the NDA's "fast-track" data.  It also unpacks, converts, and BIDS-standardizes the fast-track data so it becomes BIDS-compliant and matches that which is uploaded to collection 3165.

## 2. BIDS App Image Processing
### abcd-hcp-pipeline [https://hub.docker.com/r/dcanumn/abcd-hcp-pipeline](https://hub.docker.com/r/dcanumn/abcd-hcp-pipeline)

To run the abcdhcp-pipeline follow the installation and usage instructions in the associated documentation.

## 3. Derivatives Creation
### file-mapper: [https://github.com/DCAN-Labs/file-mapper](https://github.com/DCAN-Labs/file-mapper)

After the image processing pipeline is run only the "necessary" files for analysis are mapped into a derivatives dataset to be shared with the larger community. This mapping is done using file-mapper.

## 4. NDA Upload
### nda-bids-upload: [https://github.com/DCAN-Labs/nda-bids-upload](https://github.com/DCAN-Labs/nda-bids-upload)

Documentation for uploading data to the NDA can be found here: [https://ndabids.readthedocs.io/en/latest/](https://ndabids.readthedocs.io/en/latest/)





