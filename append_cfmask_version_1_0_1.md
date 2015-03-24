## append cfmask Version 1.0.1 Release Notes ##
Release Date: July 12, 2013

### Downloads ###

**append\_cfmask source code - available via the [cfmask and append\_cfmask Google Projects Source](http://code.google.com/p/cfmask/source/checkout) link**

  * Non-members may check out a read-only working copy anonymously over HTTP.
  * svn checkout http://cfmask.googlecode.com/svn/append_cfmask/tags/version_1.0.1 append\_cfmask-read-only

### Installation ###
Same installation instructions as for Version 1.0.0

### Dependencies ###
Same dependencies as for Version 1.0.0

### Associated Scripts ###
Same scripts as for Version 1.0.0, updated for 1.0.1.

### Verification Data ###

### User Manual ###

### Product Guide ###


## Changes From Previous Version ##
#### Updates on July 12, 2013 - USGS EROS ####
  * src
    1. Modified the application pull the fmask version from the fmask file and carry that over into the lndsr file.
    1. Modified the Makefiles to copy the .py files from the scripts directory to the $BIN directory when running "make install".

  * scripts
    1. Cleaned up a minor bug in the error handling section.