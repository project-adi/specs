# The ADI Screen Management metalanguage
## Basic info
ID: 0x40030000
stringified name: video_screenmgmt

## Structs
* modeinfo_t
```c
typedef struct {
    uint32_t width;
    uint32_t height;
    uint32_t pitch;

    uint8_t color_config;
} modeinfo_t;
```
* screen_t
```c
typedef struct {
    modeinfo_t* modes;
    uint32_t num_modes;

    uint32_t current_mode;
    uint32_t fb_id;
} screen_t;
```
* screen_list_t
```c
typedef struct {
    screen_t* screens;
    uint32_t num_screens;
}
```
## Defines
* `COLOR_CONFIG_RGB565` = 0
* `COLOR_CONFIG_RGB888` = 1
* `COLOR_CONFIG_ARGB8888` = 2
* `COLOR_CONFIG_BGRA8888` = 3

## Driver side
### Events
* `event_get_screens`(modeinfo_t mode) -> `screen_list_t` screens</br>
tied to `get_screens` 
* `event_set_mode`(uint32_t mode) -> `bool` success</br>
tied to `set_mode`

## Client side
### Functions
* `get_screens(modeinfo_t mode)` -> `screen_list_t` screens </br>
tied to `event_get_screens`
* `set_mode(uint32_t mode)` -> `bool` success </br>
tied to `event_set_mode`