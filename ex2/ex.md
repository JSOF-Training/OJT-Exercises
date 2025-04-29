# Instructions

## User mode
In this exercise you are allowed to use only open, read, write and seek system calls. In particular, functions like printf are not allowed!
Write a **user mode** program that reads from the command line:
    1.	filename  - to read from or write to
    2.	r/w  - mode (read or write)
    3.	offset - offset in file 
    4.	nbytes - number of bytes to read or write
    5.	 text - text to write if it is a write operation, if not given read it from the STDIN. reads/ writes nbytes from/to the file in the specified offset.
    - If the file filename does not exist, create a new one.
Print the read data to screen. 
Print error message to STDERR.

## Kernel mode
  1. What is a character device driver? read about it.
  2. Assume that somebody tells you a valid address in kernel space address and asks you to read from it or write to it. Is it possible to write a regular C program that will do it? In which mode does the program run? In which mode does a driver run? 
  3.  Extend the module from the previous challenge to become a character device driver. It should support reading and writing arbitrary amounts of bytes from or to a given kernel memory address.
  > Do not implement `ioctl`.
  1. How can we find a valid kernel memory address if there is no one to tell us about one? Think about a way to do it. Maybe you would ask yourself - what defines an address as valid here? Use the address you found in order to check your driver. Remember that the kernel can access any address physically accessible, try to think of an address that would be easy check and try to find it in the kernel's address space.
  > Note: If you are printing some address in a kernel process, pay attention  that `printk` may print a hashed address. Use `%px` to avoid it. 

  > Note: Pay attention to the word size of raspberry pi address (32 or 64 bit) 


