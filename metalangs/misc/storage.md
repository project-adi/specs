# The ADI Storage metalanguage
## Basic info
ID: 0x400F0000
stringified name: misc_storage

## Structs
* sdev_ident_t
```c
typedef struct {
    uint64_t size;
    uint64_t sector_size;
    bool read_only;
    //TODO: CD burning support
} sdev_ident_t;
```

## Driver side
### Events
* `event_identify`() -> `sdev_ident_t` ident</br>
tied to `identify`
* `event_transact`(`bool` write,`uint32_t` offset,`uint32_t` count,`void*` buffer) -> `uint32_t` transaction_id</br>
tied to `transact`
### Functions
* `signal_transaction_done`(`uint32_t` transaction_id) -> `bool` success</br>
tied to `event_transaction_done`

## Client side
### Events
* `event_transaction_done`(`uint32_t` transaction_id)</br>
tied to `signal_transaction_done`</br>
called when an asynchronous transaction is done
### Functions
* `identify`() -> `sdev_ident_t*` ident</br>
tied to `event_identify`
* `transact`(`bool` write,`uint32_t` offset,`uint32_t` count,`void*` buffer) -> `uint32_t` transaction_id</br>
tied to `event_transact`
