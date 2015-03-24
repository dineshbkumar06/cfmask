## cfmask Version 1.3.0 Release Notes ##
Release Date: March 28, 2014

### Downloads ###

**cfmask source code - available via the [cfmask](http://code.google.com/p/cfmask/source/checkout) Google Projects Source link**

  * Non-members may check out a read-only working copy anonymously over HTTP.
  * svn checkout http://cfmask.googlecode.com/svn/cfmask/tags/version_1.3.0 cfmask-read-only

### Installation ###
  1. Install dependent libraries - HDF-EOS GCTP, HDF4, HDF-EOS2
  1. Set up environment variables.  Can create an environment shell file or add the following to your bash shell.  For C shell, use 'setenv VAR "directory"'.
```
    export HDFINC="path_to_HDF_include_files"
    export HDFLIB="path_to_HDF_libraries"
    export HDFEOS_INC="path_to_HDFEOS_include_files"
    export HDFEOS_LIB="path_to_HDFEOS_libraries"
    export HDFEOS_GCTPINC="path_to_HDFEOS_GCTP_include_files"
    export HDFEOS_GCTPLIB="path_to_HDFEOS_GCTP_libraries"
    export ESUN="path_to_EarthSunDistance.txt_file"
```
  1. Checkout (from Google cfmask project) and install source files
```
cd cfmask/src
make
make install
```
This will create a cfmask executable under $BIN(tested in gcc  compiler)

  1. Test - Obtain a lndth.hdf file, a lndcal.hdf file, and a metadata file (from [LEDAPS](https://code.google.com/p/ledaps/)) then run the following command
```
cfmask --toarefl=path_to/lndcal.hdf
```
  1. Check output
```
fmask.<scene_name>.hdf: should contain only one fmask_band in the HDF output file
```

### Dependencies ###
  * GCTP libraries
  * HDF4 libraries
  * HDF-EOS2 libraries
  * Python 2.7 and Scipy

### Associated Scripts ###
Same scripts as for Version 1.2.1, updated for Version 1.3.0.

### Verification Data ###

### User Manual ###
See --help for details about command line options.

#### Example Usage ####
```
cfmask --toarefl=path_to/lndcal.L5010054_05420110312.hdf --prob=22.5 --cldpix=3 --sdpix=3 --write_binary --verbose
```

### Product Guide ###


## Changes From Previous Version ##
#### Updates on March 28, 2014 - USGS EROS ####

  * CFmask 1.3.0 - Based on new Fmask v3.2 matlab code.
    1. Added "--max\_cloud\_pixels < value >" option to the command line which will split clouds into two or more if the number of cloud pixels exceeds the specified value.  We will be using a value of 5 million in our processing.
      * Implemented to help reduce memory usage with large cloud scenes.
      * It does change the larger cloud shadows slightly as the cloud shadow detection based on cloud pixel BT dynamic statics values within the cloud.  It will only impact clouds with more than "the specified" pixels and also slightly alter shadow pixel locations.  Can make some cases better and other cases worse.
    1. Use a "bit" mask instead of multiple masks for different pixel types, shaved about 350 MB off the base memory usage.
    1. Minor update to scripts for memory usage.  The bug here was causing uniform scenes (snow in the identified case) to allocate huge amounts of memory due to having a significant number of pixels at the max value for the scene/band being processed.