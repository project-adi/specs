# ADI Core
This document details the core API and ABI of the ADI protocol.

## Function loading
All drivers get a pointer to the core struct as an argument called `core`.

## The Metalanguage struct
The metalanguage struct contains the following fields:
* `int` id
* `char*` stringified_name
* `char*` implementer_name
* `uint8_t` mlang_version_major
* `uint8_t` mlang_version_minor
* `uint16_t` mlang_version_build


## The Core struct
### Logging
* `core`->`log_info`(`char*` format,...)
* `core`->`log_warning`(`char*` format,...)
* `core`->`log_error`(`char*` format,...)
* `core`->`panic`(`char*` format,...)
* `core`->`exit`(`bool` success)

### Metalanguage API
* `core`->`get_metalanguage`(`char*` name) -> `metalanguage*` metalangs_implemented
* `core`->`implement_metalanguage`(`metalanguage*` metalang) -> `fptr` init_function

### Device API
* `core`->`register_device`(metalanguage_t* metalangs_implemented,`int` count) -> `int` device_id
* `core`->`unregister_device`(`int` device_id)

### Memory API
* `core`->`alloc`(`size_t` size) -> `void*` ptr
* `core`->`free`(`void*` ptr) -> `bool` success
* `core`->`realloc`(`void*` ptr,`size_t` size) -> `void*` new_ptr

* `core`->`memcpy`(`void*` dst,`const void*` src,`size_t` size) -> `bool` success
* `core`->`memset`(`void*` ptr,`int` value,`size_t` size) -> `bool` success
