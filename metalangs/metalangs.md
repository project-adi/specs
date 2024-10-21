# List of metalangs
## Architecture dependent
These metalanguages let the driver use architecture dependant instructions easily:
- <a href="arch_specific/x86.md">x86</a>
- <a href="arch_specific/x86_64.md">x86_64</a>
- <a href="arch_specific/aarch32.md">aarch32</a>
- <a href="arch_specific/aarch64.md">aarch64</a>
- <a href="arch_specific/riscv32.md">riscv32</a>
- <a href="arch_specific/riscv64.md">riscv64</a>

## Bus stuff
These matalanguages let the driver use the bus:
- <a href="bus/pci.md">PCI/PCIe</a>
- <a href="bus/usb.md">USB</a>
- <a href="bus/scsi.md">SCSI</a>

## Client-facing
These metalanguages let the driver provide their functionality:
* Time
    - <a href="time/timekeeper.md">Timekeeper</a>
    - <a href="time/timer.md">Timer</a>
* Storage
    - <a href="storage/sync.md">Synchronous Storage Device</a>
    - <a href="storage/async.md">Asynchronous Storage Device</a>
* Network
    - I have no fucking clue to put here
* HID
    - <a href="hid/kb.md">Keyboard</a>
    - <a href="hid/pointer.md">Pointing device</a>
    - <a href="hid/controller.md">Game controller</a>
    - <a href="hid/braille.md">Refreshable Braille Display</a>
    - <a href="hid/touch.md">Touchscreen</a>
    - <a href="hid/drawing.md">Graphics Tablet</a>
    - <a href="hid/cam.md">Webcam</a>
    - <a href="hid/fingerprint.md">Fingerprint scanner</a>
* Audio
    - <a href="audio/out.md">Output</a>
    - <a href="audio/in.md">Input</a>
* Video
    - <a href="video/screenmgmt.md">Screen Management</a>
    - <a href="video/fb.md">Framebuffer</a>
    - <a href="video/opengl.md">OpenGL</a>
    - <a href="video/vulkan.md">Vulkan</a>