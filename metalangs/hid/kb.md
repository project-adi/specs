# The ADI Keyboard metalanguage
## Basic info
ID: 0x00020000

## Driver side
### Events
`poll`(`char*` buffer,`uint32` amt) -> `bool` success
### Functions
`send_event_key`(`char` scancode) -> `bool` success

## Client side
### Events
`event_key`(`char` scancode)
### Functions
`get_key`(`char*` buffer,`uint32` amt) -> `bool` success
