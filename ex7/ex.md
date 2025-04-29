# Instructions

In this task we assume that we have a buggy driver that we've exploited thus giving us an InfoLeak (the ioctl that returns the address of the current `task_struct`) and a limited Read/Write primitive (the read/write operations). Assume that the write operation is really unstable, each time you write there is a good chance that the kernel might panic so limit yourself to a few of these as possible.

## User mode privilege escalation

1. Find a way to provide stable access to kernel memory without the driver given you can perform a limited amount of driver operations as a setup. You may write a python script to test you thesis.
2. Once this capability is achieved, add a command line argument to the C tool that performs a finite amount of read/write operations using driver, then enters the tool's live interpreter mode which would allow reading from and writing to any kernel address **without** invoking the driver at all.

# Notes

1. There are two ways to solve this problem, read the hints if you've solved it and would like learn more.
