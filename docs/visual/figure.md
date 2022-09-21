# Figure Maker

## Overview

It can often be difficult to standardize the way figures are made in the connectome workbench view.  Furthermore, workbench does not have an easy way to generate brain images automatically from the command line.  Nobody wants to manually create thousands of images.  The figure maker is a python wrapper for a bash script (make_dscalar_pics_vX.X.sh).  The script uses a template scene file and uses a(n exhausting) list of sed commands to replace the file names and parameters within the scene file to generate an image file.

## Code Locations

DCAN labs members can find the code here:
/home/faird/shared/code/internal/utilities/figure_maker

You can find the version-controlled code on [gitlab](https://gitlab.com/Fair_lab/figure-maker).
