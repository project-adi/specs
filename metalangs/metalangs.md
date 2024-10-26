# Metalanguage IDs
a metalanguage ID is a 32 bit number unique to each metalanguage. While it can be anything, it should be interpreted as 16 bits of grup ID and 16 bits of metalanguage ID.

# Metalnaguage orientation
a metalanguage can be:
 - Hardware-facing(`0x0000xxxx`,<a href="hw_facing_template.md">template</a>)
 - Client-facing(`0x4000xxxx`,<a href="client_facing_template.md">template</a>)
 - Loopback(`0x8000xxxx`,<a href="loopback_template.md">template</a>)


# Hardware facing metalnaguages
* Architecture dependent(`0x0000xxxx`)
    These metalanguages let the driver use architecture dependant instructions easily:
    <!-- - <a href="arch_specific/x86.md">x86</a> -->
    - <a href="arch_specific/x86_64.md">x86_64</a>
    <!-- > - <a href="arch_specific/aarch32.md">aarch32</a>
    - <a href="arch_specific/aarch64.md">aarch64</a>
    - <a href="arch_specific/riscv32.md">riscv32</a>
    - <a href="arch_specific/riscv64.md">riscv64</a> -->

* Buses(`0x0001xxxx`)
    - <a href="bus/pci.md">PCI/PCIe</a>
    <!-- - <a href="bus/usb.md">USB</a>
    - <a href="bus/scsi.md">SCSI</a> -->

# Client-facing metalanguages
These metalanguages let the driver provide their functionality:
<!-- * Network(`0x4000xxxx`)
    - I have no fucking clue to put here -->
* HID(`0x4001xxxx`)
    - <a href="hid/kb.md">Keyboard</a>
    - <a href="hid/pointer.md">Pointing device</a>
    <!-- - <a href="hid/controller.md">Game controller</a>
    - <a href="hid/braille.md">Refreshable Braille Display</a>
    - <a href="hid/touch.md">Touchscreen</a>
    - <a href="hid/drawing.md">Graphics Tablet</a>
    - <a href="hid/cam.md">Webcam</a>
    - <a href="hid/fingerprint.md">Fingerprint scanner</a> -->
<!--* Audio(`0x0002xxxx`)
    - <a href="audio/out.md">Output</a>
    - <a href="audio/in.md">Input</a>-->
* Video(`0x4003xxxx`)
    - <a href="video/screenmgmt.md">Screen Management</a>
    - <a href="video/fb.md">Framebuffer</a>
    <!-- - <a href="video/opengl.md">OpenGL</a>
    - <a href="video/vulkan.md">Vulkan</a> -->
* Misc(`0x400Fxxxx`)
    - <a href="misc/storage.md">Storage</a>
    - <a href="misc/timekeeper.md">Timekeeper</a>

<!--## Custom metalanguages(`0xFFxxxxxx`)
TODO: add a way for users to define custom metalanguages -->