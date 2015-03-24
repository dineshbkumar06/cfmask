## append\_cfmask Version 1.0.0 Release Notes ##
Release Date: June 11, 2013

### Downloads ###

**append\_cfmask source code - available via the [cfmask and append\_cfmask Google Projects Source](http://code.google.com/p/cfmask/source/checkout) link**

### Installation ###
  1. Install dependent libraries - HDF-EOS GCTP, HDF4, HDF-EOS2, JPEG
  1. Set up environment variables.  Can create an environment shell file or add the following to your bash shell.  For C shell, use 'setenv VAR "directory"'.  Note: If the HDF library was configured and built with szip support, then the user will also need to add an environment variable for SZIP include (SZIPINC) and library (SZIPLIB) files.
```
    export HDFEOS_GCTPINC="path_to_HDF-EOS_GCTP_include_files"
    export HDFEOS_GCTPLIB="path_to_HDF-EOS_GCTP_libraries"
    export HDFINC="path_to_HDF_include_files"
    export HDFLIB="path_to_HDF_libraries"
    export HDFEOS_INC="path_to_HDFEOS_include_files"
    export HDFEOS_LIB="path_to_HDFEOS_libraries"
    export JPEG_INC="path_to_JPEG_include_files"
    export JPEG_LIB="path_to_JPEG_libraries"
    export BIN="path_to_directory_for_append_cfmask_binaries"
```
  1. Checkout (from Google cfmask project) and install source files
```
cd append_cfmask/src
make
make install
```
This will create an append\_cfmask executable under $BIN(tested in gcc  compiler)

**Note that if the HDF library was configured and built with szip support, then the user will also need to add "-L$(SZIPLIB) -lsz" at the end of the library defines in the Makefiles.  The user should also add "-I$(SZIPINC)" to the include directory defines in the Makefile.**

  1. Test - Obtain an lndsr.hdf (from LEDAPS) and fmask.hdf (from cfmask) then run the following command
```
append_cfmask -sr <lndsr_HDF_file> -cfmask <cfmask_HDF_file>
```
Or simply run the python script in the append\_cfmask/scripts directory, which is copied to $BIN when running make install.
```
do_append_cfmask.py --sr_infile=<lndsr_HDF_file> --cfmask_infile=<cfmask_HDF_file>
```
  1. Check output
```
lndsr.hdf: should now contain the fmask band as an additional SDS in the lndsr.hdf product
```

### Dependencies ###
  * GCTP libraries
  * JPEG libraries
  * HDF4 libraries
  * HDF-EOS2 libraries

### Verification Data ###

### User Manual ###

### Product Guide ###

## Changes From Previous Version ##
This is the initial release of this software.