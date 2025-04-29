# Reading material

Linux Kernel Development (chapters: 15)

# Instructions

## Userland

1. Write a script that uses the C tool that finds and lists all the mapped memory ranges in a given process's virtual memory space.
2. Assuming that in the previous sections you somehow retrieved the compiled constant offsets of the various structures (`task_struct`, `mm_struct`, etc..) in order to read values from your script, now upgrade the script so that it can deduce these offsets automatically during runtime (and theoretically work with other builds of linux).

# Notes

1. If you found the address of a field you may deduce the offsets of simple adjacent fields (i.e. primitive types, simple types with no ifdefs, obvious ifdefs like whether multiprocessing is enabled).
