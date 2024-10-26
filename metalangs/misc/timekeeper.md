# The ADI Timekeeper metalanguage
## Basic info
ID: 0x400F0001
stringified name: misc_timekeeper

## Structs
* time_t
```c
typedef struct {
    uint32_t year;
    uint8_t month;
    uint8_t day;
    uint8_t hour;
    uint8_t min;
    uint8_t sec;
    uint8_t usec;
    uint8_t nsec;
} time_t;
```

## Driver side
### Events
* `event_get_time`() -> `time_t` time</br>
tied to `get_time`
* `event_set_time`(time_t time) -> `bool` success</br>
tied to `set_time`
* `event_get_time_unix`() -> `uint64_t` time</br>
tied to `get_time_unix`
* `event_set_time_unix`(`uint64_t` time) -> `bool` success</br>
tied to `set_time_unix`

## Client side
### Functions
* `get_time`() -> `time_t` time</br>
tied to `event_get_time`
* `set_time`(time_t time) -> `bool` success</br>
tied to `event_set_time `
* `get_time_unix`() -> `uint64_t` time</br>
tied to `event_get_time_unix`
* `set_time_unix`(`uint64_t` time) -> `bool` success</br>
tied to `event_set_time_unix`