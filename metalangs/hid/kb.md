# The ADI Keyboard metalanguage
## Basic info
ID: 0x00020000

## Driver side
### Events
* `event_poll`(`char*` buffer,`uint32` amt) -> `bool` success</br>
tied to `poll` 
### Functions
* `send_event_key`(`char` scancode) -> `bool` success</br>
tied to `event_key`
## Client side
### Events
* `event_key`(`char` scancode)</br>
tied to `send_key`
### Functions
* `poll`(`char*` buffer,`uint32` amt) -> `bool` success</br>
tied to `event_poll`