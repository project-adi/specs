# ADI Core
This document details the core API and ABI of the ADI protocol.

## Function loading
All drivers get a pointer to the Core Function Region(CFR) as an argument called `core`.

# The Core struct
## Metalanguages
* `core`->`arch_x86_64`
* `core`->`bus_pci`
* `core`->`hid_kb`
* `core`->`hid_pointer`
* `core`->`video_screenmgmt`
* `core`->`video_fb`
* `core`->`misc_storage`
* `core`->`misc_timekeeper`

## Logging
* `core`->`log_info`(`char*` format,...)
* `core`->`log_warning`(`char*` format,...)
* `core`->`log_error`(`char*` format,...)
* `core`->`panic`(`char*` format,...)
* `core`->`exit`(`bool` success)

## Device API
* `core`->`register_device`(metalanguage_t* metalangs_implemented,`int` count) -> `int` device_id
* `core`->`unregister_device`(`int` device_id)

## Memory API
* `core`->`alloc`(`size_t` size) -> `void*` ptr
* `core`->`free`(`void*` ptr) -> `bool` success
* `core`->`realloc`(`void*` ptr,`size_t` size) -> `void*` new_ptr

* `core`->`memcpy`(`void*` dst,`const void*` src,`size_t` size) -> `bool` success
* `core`->`memset`(`void*` ptr,`int` value,`size_t` size) -> `bool` success
