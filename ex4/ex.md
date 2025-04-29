# Instructions

## User mode

1. Add a "Live interpreter" mode to your C tool so that many sequential commands can be executed (ioctl, read, write, ...) and the process is **not** created and destroyed in the background.
2. Write a python script that uses the previous tool written in C to acquire an address of some `task_struct`. Once you have an address of a `task_struct`, once again using the previous tool, iterate over all running processes on the system and print their PID, name (`comm` is fine) and `task_struct` address. What you should have is a `ps`-like utility.

# Notes

No need to be concerned with any locks.

You may use any library to assist you in parsing, we used [dholm](https://github.com/dholm) / [cliparser](https://github.com/dholm/cliparser).
