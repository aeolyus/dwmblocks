# dwmblocks
Modular status bar for dwm written in C.

## Installation
Modify blocks to your liking and then (as root if necessary)
```
make clean install
```

## Modifying Blocks
The statusbar is made from text output from commandline programs.
Blocks are added and removed by editing the `blocks.h` header file.

## Signaling Changes
Most statusbars update themselves by rerunning their scripts every few seconds.
While that is an option, you can also have each module update independently
on an event rather than constantly rerunning.

For example, if the volume module listens to signal `n` and can be updated with
```
pkill -RTMIN+n dwmblocks
```
> **NOTE**: sending an unexpected signal will likely cause it to crash.
