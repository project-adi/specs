# The ADI driver file format
TODO: support other architectures than x86_64
### Endianness
everything is little endian

### magic number 
The magic number is `0x4C4F4F4B20494441`(ASCII "`ADI KOOL`")

### Header
other fields in the header:
* Version(`2` bytes): version of the ADI specification used
* Init routine entry point(`8` bytes): pointer to the init routine in memory(drivers are NEVER relocatable)
* Driver name(`2` bytes): offset into the string table for the driver's name
* Author name(`2` bytes): offset into the string table for the author's name
* Driver version(`3` bytes): `1` byte for the major version, `1` byte for the minor version and `1` byte for the patch
* Metalanguage table offset(`4` bytes): offset of the metalanguage table in the file
* Metalanguage table size(`4` bytes): size of the metalanguage table
* String table offset(`4` bytes): offset of the string table in the file
* String table size(`4` bytes): size of the string table
* Segment table offset(`4` bytes): offset of the segment table in the file
* Segment table size(`4` bytes): size of the segment table
* Content region offset(`4` bytes): offset of the content region
* CFR address(`8` bytes): address to load the CFR pointer to

### String table
The string table just has strings lul.

### Segment table
One entry contains:
* Name(`2` bytes): offset into the string table for the segment's name
* Offset(`4` bytes): offset of the segment in the file in relation to the content region(only if infile is true)
* Size(`4` bytes): size of the segment
* Virtual Address(`8` bytes): virtual address of the segment
* Flags(`1` byte): see the list bellow

#### Segment flags field
* bit `0` = executable
* bit `1` = writable
* bit `2` = readable
* bit `3` = infile(Is it in the file or is it just all zeroes)
* bit `4` = paging access
* bit `5` = metadriver
* bit `6` = userspace access
* bit `7` = reserved

### Metalanguage table
One entry contains:
* ID(`4` bytes): ID of the metalanguage
* ptr_addr(`4` bytes): memory adress to put the pointer to the metalanguage struct at