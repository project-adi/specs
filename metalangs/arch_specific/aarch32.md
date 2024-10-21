# The ADI aarch32 specific metalanguage

## Structs
* context_t
```c
typedef struct {
    uint32_t r0;
    uint32_t r1;
    uint32_t r2;
    uint32_t r3;
    uint32_t r4;
    uint32_t r5;
    uint32_t r6;
    uint32_t r7;
    //etc. this is just an example
} context_t;
```
## Defines
defines of the metalanguage id needed
### Functions
* `bool register_irq(uint IRQ, void (*handler)(context_t*))`