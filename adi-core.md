# ADI Core 
This document details the core API and ABI of the ADI protocol.
## Function loading
All drivers get a pointer to the Core Function Region(CFR) as a global variable called `core`.
all functions are in `core`(e.g. "core->alloc(...)")
## Metalanguage loading
You must define a variable for all metalanguages in the config file with their name, ADIkit registers them, and fills the `ptr_addr` field with the address to the metalanguage pointer.

The kernel loading it then takes the struct for the metalanguage, and initializes a struct, and puts the pointer to it into the varable you defined.
## Regions
A region is a distinct part of the driver that is respoinsible for one simple task. it may only implement one `client facing` metalanguage.

all segments belong to a region: their names are constructed like `<region>.<segment>`.
## Management API
* log_info
* log_warning
* log_error
* panic
* register_device
* unregister_device
## Memory API
* alloc
* free
* realloc