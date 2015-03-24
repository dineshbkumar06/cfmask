## cfmask Version 1.1.1 Release Notes ##
Release Date: July 18, 2013

### Downloads ###

**cfmask source code - available via the [cfmask and cfmask Google Projects Source](http://code.google.com/p/cfmask/source/checkout) link**

### Installation ###
  1. Install dependent libraries - HDF-EOS GCTP, HDF4, HDF-EOS2, openCV  # Set up environment variables.  Can create an environment shell file or add the following to your bash shell.  For C shell, use 'setenv VAR "directory"'.
```
    export HDFINC="path_to_HDF_include_files"
    export HDFLIB="path_to_HDF_libraries"
    export HDFEOS_INC="path_to_HDFEOS_include_files"
    export HDFEOS_LIB="path_to_HDFEOS_libraries"
    export HDFEOS_GCTPINC="path_to_HDFEOS_GCTP_include_files"
    export HDFEOS_GCTPLIB="path_to_HDFEOS_GCTP_libraries"
    export OPENCVINC="path_to_OpenCV_include_files"
    export OPENCVLIB="path_to_OpenCV_libraries"
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
  * openCV libraries
  * HDF4 libraries
  * HDF-EOS2 libraries
  * Python 2.7 and Scipy

### Verification Data ###

### User Manual ###

### Product Guide ###

## Changes From Previous Version ##
This is the initial release of cfmask with Geo-Australian image fill function used.