## CFmask Version 1.4.0 Release Notes ##
Release Date: July 29, 2014

### Downloads ###

**CFmask source code - available via the [cfmask](http://code.google.com/p/cfmask/source/checkout) Google Projects Source link**

  * Non-members may check out a read-only working copy anonymously over HTTP.
  * svn checkout http://cfmask.googlecode.com/svn/cfmask/tags/version_1.4.0 cfmask-read-only

### Dependencies ###
  * ESPA raw binary libraries and tools in the [espa\_common](https://code.google.com/p/espa-common/) Google Project
  * Python 2.7 and Scipy

### Installation ###
  1. Install dependent libraries - LIBXML2, ESPA\_COMMON
  1. Set up environment variables.  Can create an environment shell file or add the following to your bash shell.  For C shell, use 'setenv VAR "directory"'.
```
    export XML2INC="path_to_LIBXML2_include_files"
    export XML2LIB="path_to_LIBXML2_libraries"
    export ESPAINC="path_to_ESPA_COMMON_include_files"
    export ESPALIB="path_to_ESPA_COMMON_libraries"
    export ESUN="path_to_EarthSunDistance.txt_file" # included with source
```
  1. Checkout (from Google cfmask project) and install source files
```
cd cfmask/src
make
make install
```
This will create a cfmask executable under $BIN(tested in gcc  compiler)

  1. Test - Obtain TOA and BT bands along with the ESPA metadata XML file (from [LEDAPS](https://code.google.com/p/ledaps/) output) then run the following command
```
cfmask --xml=<scene_id>.xml
```
  1. Check for output of a raw binary fmask band with an associated ENVI header
```
<scene_id>_fmask.hdr
<scene_id>_fmask.img
```

### Associated Scripts ###
Same scripts as for Version 1.3.1.

### Verification Data ###

### User Manual ###
See "cfmask --help" for details about command line options.

Only TM(L4, L5) and ETM+(L7) sensors are supported in this version of CFmask.

#### Example Usage ####
```
cfmask --xml=LT50770132008180GLC00.xml --prob=22.5 --cldpix=3 --sdpix=3 --write_binary --verbose
```

### Product Guide ###


## Changes From Previous Version ##
#### Updates on July 29, 2014 - USGS EROS ####

  * CFmask 1.4.0 - Based on Fmask v3.3 matlab code.
    1. Modified to use the ESPA internal file format for input and output.  The ESPA internal format provides a metadata file in XML format along with raw binary data files that each have an associated ENVI header.