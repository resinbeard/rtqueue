#RTQueue
Non-blocking queue for JACK audio data

This header file provides a non-blocking queue intended for JACK samples, but easily repurposed for other soft realtime applications. First used in Ficus, I found it useful for multiple JACK-related projects so it gets its own repository.

## Dependencies
 - [JACK](http://jackaudio.org/)

## Building
Copy the header file into your dev directory and include with your application source

## Getting Started
```
#include "rtqueue.h"

float data;
rtqueue_t *fifo_out = rtqueue_init(10000);

while(1)
    if( !rtqueue_isempty(fifo_out) )
        data = rtqueue_deq(fifo_out);

```
