## cfmask Version 1.1.3 Release Notes ##
Release Date: September 3, 2013

### Downloads ###

**cfmask source code - available via the [cfmask Google Projects Source](http://code.google.com/p/cfmask/source/checkout) link**

### Installation ###
Same installation instructions as for Version 1.1.1

### Dependencies ###
Same dependencies as for Version 1.1.1

### Associated Scripts ###
Same scripts as for Version 1.1.1, updated for 1.1.1.

### Verification Data ###

### User Manual ###
./cfmask --toarefl=/home/sguo/LEDAPS/ledaps-read-only/ledapsSrc/src/fmask2/lndcal.L5010054\_05420110312.hdf --prob=22.5 --cldpix=3 --sdpix=3 --write\_binary --verbose

### Product Guide ###


## Changes From Previous Version ##
#### Updates on July 12, 2013 - USGS EROS ####
  * src
    1. Modified cfmask code to read each band gain/bias from HDF attributes instead of from LEDAPS metadata file (need LEDAPS 1.3.1). Need TOA reflectance file instead of metadata file as input.
    1. Added in upside down scene handling for polar steoreographic scene in cfmask.
    1. Standardized code per peer-review comments on version 1.1.2.

  * scripts
    1. Modified fillminima.py add in when boundaryval is 0.0, then set it to hMax, which will fix the whole water scene when no land clear-sky pixel existed scenario for cfmask code.
    1. Standardized code per peer-review comments on version 1.1.2.