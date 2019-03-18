# zig-sdl

Self-contained SDL2 package for Zig.

## Current Status

I've only experimented with Linux so far. I was able te build
libSDL2.a and then link an application against it, but there
would be no video support:

```
$ zig build run
INFO: Unable to initialize SDL: No available video device
```

So then I tried enabling X11, and running into this:

```
/home/andy/dev/zig-sdl/src/sensor/../events/../video/./khronos/vulkan/./vk_platform.h:113:10: fatal error: 
      'X11/Xlib.h' file not found
#include <X11/Xlib.h>
         ^~~~~~~~~~~~
1 error generated.
```

Which means that I need to create an X11 package that this one will depend on.
Recursive package dependencies is starting to get into territory where we need
Zig package manager to continue.

## How to Use this Package

I'm still experimenting. Don't try to use it yet.
