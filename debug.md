# Debug

How to debug with QEMU + GDB?

This will only cover specifics, you have to know GDB debugging already.

First read the `make debug` target to get started. Those points will not be repeated here.

How to have debug symbols: <http://stackoverflow.com/a/32960272/895245> TODO implement here. Needs to point GDB to an ELF file in addition to the remote listen.

How to step over `int` calls: <http://stackoverflow.com/questions/24491516/how-to-step-over-interrupt-calls-when-debugging-a-bootloader-bios-with-gdb-and-q>

Single stepping until a given opcode can be helpful sometimes: <http://stackoverflow.com/a/31249378/895245>

TODO: detect if we are on 16 or 32 bit automatically from control registers. Now I'm using 2 functions `16` and `32` to switch  manually, but that sucks. The problem is that it's not possible to read them directly: <http://stackoverflow.com/a/31340294/895245> If we had `cr0`, it would be easy to do with an `if cr0 & 1` inside a hook-stop.

TODO: Take segmentation offsets into account: <http://stackoverflow.com/questions/10354063/how-to-use-a-logical-address-in-gdb>
