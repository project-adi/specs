# The ADI driver file format
The ADI driver file format is a binary file format used to store drivers for the ADI driver interface. Its goal is to encode an ADI driver in a way that is small and fast to load. For this reason the format does not support relocation. 

## Platform specifics
The ADI driver aims to be platform independent, but it has limitations:
* No support for bottom half kernels
* No support for more than 64 bit architectures
* 

## Structure
The ADI driver file consists of the following sections:
* Header
* Segment table
* Content region

### Header
other fields in the header:
* Magic number(`4` bytes): magic number `0x46494441`(ASCII "`ADIF`")
* ADI Version(`2` bytes): version of the ADI specification used
* Architecture(`2` bytes): target architecture, defined as the same as ELF's `e_machine` field
* Init routine entry point(`8` bytes): pointer to the init routine in memory
* Driver name(`64` bytes): the driver's name(`64` characters)
* Author name(`64` bytes): the author's name(`64` characters)
* Major version(`1` byte): major version of the driver
* Minor version(`1` byte): minor version of the driver
* Build number(`2` bytes): build number of the driver
* Segment table offset(`4` bytes): offset of the segment table in the file
* Segment table size(`4` bytes): size of the segment table

### Segment table
One entry contains:
* Name(`2` bytes): offset into the string table for the segment's name
* Offset or Filler(`4` bytes): offset of the segment in the file or filler if bit `2` of flags is not set 
* Size(`4` bytes): size of the segment
* Virtual Address(`8` bytes): virtual address of the segment
* Flags(`1` byte): see the list bellow

#### Segment flags field
* bit `0` = Whether the segment is executable
* bit `1` = Whether the segment is writable
* bit `2` = Whether the segment is present in the content region
* bit `3` = reserved
* bit `4` = reserved
* bit `5` = reserved
* bit `6` = reserved
* bit `7` = reserved

### Content region
The content region is a blob of code or data. It contains the content of segments. 
*Note: the content region is not guaranteed to be page aligned*