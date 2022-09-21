# Cifti Conn Matrix

## Overview

One crucial way that we explore brain function is to explore the functional connectivity of the brain.  The way we do that is by determining the correlation of the fluctuations in the BOLD signal over time. That’s another way of saying that we are interested in the voxel-to-voxel (or grayordinate-to-grayordinate or parcel to parcel) correlation.  Exactly how this is done can greatly affect the correlation structure of the data.  The final result is a matrix of correlations. For example, a correlation matrix that does not use any motion censoring will almost certainly look different that one that does use motion censoring.  A correlation matrix with many time points will be much more reliable than one with few time points.

## Code Locations

DCAN labs members can find the code here:
/home/faird/shared/code/internal/utilities/cifti_connectivity

The code is version controlled on [github](https://github.com/DCAN-Labs/cifti-connectivity.git).