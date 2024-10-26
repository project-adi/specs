# ADI framebuffer metalanguage
## Basic info
ID: 0x40030001
stringified name: video-fb

## Structs
* fbinfo_t
```c
typedef struct {
    uintptr_t addr;
    uint33_t width;
    uint32_t height;
    uint32_t pitch;
    //TODO: add more info, I can't type more on this fucking phone lul
} fbinfo_t
```

## Driver side
### Events
* `fbinfo_t framebuffer_request(uint FBID)`</br>
tied to `get_fbinfo`

## Client side
### Functions
* `fbinfo_t get_fbinfo(uint FBID)` </br>
tied to `framebuffer_request`