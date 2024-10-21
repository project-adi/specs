# The ADI aarch64 specific metalanguage

## Structs
* context_t
```c
typedef struct {
    uint32_t x0;
    uint32_t x1;
    uint32_t x3;
    uint32_t x4;
    uint32_t x5;
    uint32_t x6;
    uint32_t x7;
    uint32_t x8;
    //etc. this is just an example
} context_t;
```
## Defines
defines of the metalanguage id needed
### Functions
* `bool register_irq(uint IRQ, void (*handler)(context_t*))`