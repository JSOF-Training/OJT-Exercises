# Linux Warm Up

## Instructions

These tasks may be completed on WSL, no rpi necessary yet.

For each task, Write a script/program (bash / Python / lua /C++/C/Rust) that accomplishes it.

* For a selected process (given pid), find **all the files** that are **mapped** to that process's memory and the addresses the files are mapped to.

  Example:

  ![](../media/image1.png)
* For a specific file (file **path,** which can represent many kinds of files - i.e “In Linux, everything is a File”), find **all** the processes that **currently** have the file opened, and the attributes it is opened with.

  Example

  ![Alt text](../media/image2.png)

## Guidelines

* [ ] The above tasks should be easy, don't overcomplicate it.
* [ ] recomended to use C/C++ using Linux headers & API due to the fact it gives you a better understanding of Linux internals (Do I really know what are the implications of some piece of code I'm writing / borrowed from someone

  else?) and exploitation abilities in a constrained environment such as in the case of crafting a limited size shellcode (which might be limited to calling syscalls only) or a sandbox.

  Note: For C language, You’ll need to install *build-essential in Ubuntu for gcc*
* [ ] Don't mix between languages for now , write each solution in a single language (But you can try to solve them with a different one each time).
* [ ] Calling bash utilities/binaries/commands is allowed only from bash (Otherwise it won't “make sense” and will cost in an overhead of creating another process when using common/popular methods).
* [ ] Linux was designed in such a way (Filesystem, Kernel & process data structures) that allows it to efficiently lookup/search/query for useful and critical information to determine the relationships between objects in memory & disk. Research what already exists and try to understand what has led to these decisions.
* [ ] Don't be afraid to dive into the source code of Linux, The goal is for you to be able to develop your own tools and to be able to understand how existing open & closed source accomplish their goal (such as those which comes with Linux in binary form)
