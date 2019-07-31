# Test setting
This bug has been reproduced in meson 0.50.1 on MacOS X High Sierra 10.13.6

# Summary
Cannot directly sum arrays and include_directories(''):

# Reproduce
## This Works
```meson
ic = []
ic += include_directories('.')
```

## This Fails
```meson
ic = [] + include_directories('.')
```

# Run example

From repository root run
```
➜  bug_include_directories git:(master) meson build      
The Meson build system
Version: 0.50.1
Source dir: /Users/leogermond/Lab/meson/bug_include_directories
Build dir: /Users/leogermond/Lab/meson/bug_include_directories/build
Build type: native build
Project name: a
Project version: undefined
Native C compiler: cc (clang 10.0.0 "Apple LLVM version 10.0.0 (clang-1000.10.44.4)")
Build machine cpu family: x86_64
Build machine cpu: x86_64

fails/meson.build:1:0: ERROR: Invalid use of addition: can only concatenate list (not "IncludeDirsHolder") to list

A full log can be found at /Users/leogermond/Lab/meson/bug_include_directories/build/meson-logs/meson-log.txt
```
