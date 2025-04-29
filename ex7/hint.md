There are two ways:

1. When you wrote the driver and copied data from the user's virtual address space to the kernel's address space, did you simply use `memcpy` or did you use a specialized function? Why is that function required? What does it do? Once you figure out how to pass that check, try to find a way to exploit it. That is, first test your thesis using your driver, then think where else this function is called where you control it's arguments.
2. How does memory access work in user mode processes? Look [here](https://www.kernel.org/doc/gorman/html/understand/understand006.html). Can you access these tables using your R/W primitive? (spoiler: yes, you can!).
