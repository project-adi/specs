# ADI Core
This document details the core API and ABI of the ADI protocol.

## Function loading
All drivers get a pointer to the Core Function Region(CFR) as a global variable called `core`.
all functions are in `core`(e.g. "core->alloc(...)")

## Metalanguage loading
You must define a variable for all metalanguages in the config file with their name, ADIkit registers them, and fills the `ptr_addr` field with the address to the metalanguage pointer.

The kernel loading it then takes the struct for the metalanguage, and initializes a struct, and puts the pointer to it into the varable you defined.

## Logging API
* `core`->`log_info`(`char*` format,...)
* `core`->`log_warning`(`char*` format,...)
* `core`->`log_error`(`char*` format,...)
* `core`->`panic`(`char*` format,...)

## Device API
* `core`->`register_device`(metalanguage_t* metalangs_implemented,`int` count) -> `int` device_id
* `core`->`unregister_device`(`int` device_id)

## Memory API
* `core`->`alloc`(`size_t` size) -> `void*` ptr
* `core`->`free`(`void*` ptr) -> `bool` success
* `core`->`realloc`(`void*` ptr,`size_t` size) -> `void*` new_ptr

* `core`->`memcpy`(`void*` dst,`const void*` src,`size_t` size) -> `bool` success
* `core`->`memset`(`void*` ptr,`int` value,`size_t` size) -> `bool` success
