## cfmask Version 1.2.1 Release Notes ##
Release Date: January XX, 2014

### Downloads ###

**cfmask source code - available via the [cfmask Google Projects Source](http://code.google.com/p/cfmask/source/checkout) link**

  * Non-members may check out a read-only working copy anonymously over HTTP.
  * svn checkout http://cfmask.googlecode.com/svn/cfmask/tags/version_1.2.1 cfmask-read-only

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
This will create an cfmask executable under $BIN(tested in gcc  compiler)

  1. Test - Obtain a lndth.hdf file, a lndcal file, and a metadata file (from LEDAPS) then run the following command
```
cfmask --metadata=input_metadata_filename_with_full_path
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
Same scripts as for Version 1.1.1, updated for 1.2.1.

### Verification Data ###

### User Manual ###
./cfmask --toarefl=/path\_to/lndcal.L5010054\_05420110312.hdf --prob=22.5 --cldpix=3 --sdpix=3 --write\_binary --verbose

### Product Guide ###


## Changes From Previous Version ##
#### Updates on January XX, 2014 - USGS EROS ####

  * CFmask 1.2.0 - Based on new Fmask v3.2 matlab code.
    1. Removed usage of openCV image\_dilute routine.
    1. Use a dynamic cloud over water threshold instead of a fixed value.
    1. Remove the use of majority-filter functions on cloud pixels.
    1. Remove the temperature screen for snow masking (because of omission of snow and this has also changed in MODIS C6).
    1. Remove  the high probability test (because of constant false cloud masking).
    1. Remove the opencv image\_dilute function usage, instead using my self-implemented "image\_dilate" which simulates the matlab image dilute used in Fmask code exactly. But my default "dilute\_buffer" is 2\*2+1 = 5 pixels instead of 2\*3+1 = 7 pixels in Fmask.
    1. Fixed a few bugs, couple of them are in Fmask matlab code and couple of them are in CFmask code.
  * CFmask 1.2.1 - Code cleanup and memory usage enhancements.
    1. Minor update to scripts for memory usage.
    1. Updates to source for memory usage.