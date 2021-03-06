C VM
This is a C implementation of kalinet OS' native words. It allows kalinet OS to run natively on any POSIX environment.

Requirements
You need curses to build the forth executable.

Build
Running make will yield forth and stage executables.

Usage
To play around kalinet OS, you'll want to run ./forth. Refer to doc/intro.txt for help.

The program is a curses interface with a limited, fixed size so that it can provide a AT-XY interface. If you wish to change the size of that screen, you need to modify COLS and LINES in both forth.c and forth.fs.

You can get a REPL by launching the program with rlwrap(1) like this:

rlwrap -e '' -m -S '> ' ./forth /dev/stdin
Problems?
If the forth executable works badly (hangs, spew garbage, etc.), it's probably because you've broken your bootstrap binary. It's easy to mistakenly break. To verify if you've done that, look at your git status. If stage.bin is modified, try resetting it and then run make clean all. Things should go better afterwards.

A modified blkfs can also break things (although even with a completely broken blkfs, you should still get to prompt), you might want to run make pack to ensure that the blkfs file is in sync with the contents of the blk/ folder.

If that doesn't work, there's also the nuclear option of git reset --hard and git clean -fxd.

If that still doesn't work, it might be because the current commit you're on is broken, but that is rather rare.
