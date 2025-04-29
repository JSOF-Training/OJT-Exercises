# Instructions

## Userland
1. Currently, using our driver we can access any memory in the kernel as it is mapped for all processes in the system. Write a script that'll be able to write to any **virtual** address of a process, again using the C tool. That is, the input to the script is a PID, a virtual address in that PID's virtual address space, whether to perform a read or write operation and optionally some data in case of a write operation. The results would be to print the data or have the given data be written to the process' memory.

# Notes
1. Don't worry about paged-out pages, you can either ignore them or deny their existence altogether.