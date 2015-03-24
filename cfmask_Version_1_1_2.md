## cfmask Version 1.1.2 Release Notes ##
Release Date: July 31, 2013

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

### Product Guide ###


## Changes From Previous Version ##
#### Updates on July 12, 2013 - USGS EROS ####
  * src
    1. Added map info to the envi header and increased MAX\_CLOUD\_TYPE to 3,000,000 which will fix all error out scenes in cfmask version\_1.1.0.
    1. Modified the Makefiles to copy the .py files from the scripts directory to the $BIN directory when running "make install".
    1. Added land cloud threashold setting when no land-clear-pixel existed in the scene.

  * scripts
    1. Modified fillminima.py and run\_fillminima.py to add in some error checks.