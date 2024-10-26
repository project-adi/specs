# The ADI Pointer metalanguage
## Basic info
ID: 0x00020001

## Driver side
### Functions
* `send_delta`(`uint32_t` x, `uint32_t` y) -> `bool` success</br>
tied to `event_delta`
* `send_button`(`uint32_t` button, `bool` down) -> `bool` success</br>
tied to `event_button`
## Client side
### Events
* `event_delta`(`uint32_t` x, `uint32_t` y)</br>
tied to `send_delta`
* `event_button`(`uint32_t` button, `bool` down)</br>
tied to `send_button`