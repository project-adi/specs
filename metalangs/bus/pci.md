# The ADI PCI/PCIe metalanguage
## Basic info
ID: 0x00010000
stringified name: bus_pci

### Functions
`pci_read`(`uint8_t` bus, `uint8_t` device, `uint8_t` func, `uint8_t` offset) -> `uint8_t` value</br>
reads an 8-bit value from a PCI device's configuration space

`pci_write`(`uint8_t` bus, `uint8_t` device, `uint8_t` func, `uint8_t` offset, `uint8_t` value) -> `void`</br>
writes an 8-bit value to a PCI device's configuration space

this is really all I could think of for now