# Instructions

## Kernel mode
- What is a `task_struct`? read about it.
- We now want to figure out the address of the current process `task_struct`.
- Add an `ioctl` function in your character device driver that will return it.
## User mode
 - Write an interactive command line tool in C that utilizes the driver to perform simple read/write operations to a specified address and retrieve a `task_struct` pointer.

