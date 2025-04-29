# Reading material

Linux Kernel Development (chapters: 3, 5, 6, 7, 8, 9, 10, 12, 15, 17)

# Instructions

1. Make sure you have SSH access to your RPI.
2. Create a simple “hello world” linux kernel module for the RPI and build, load and unload it from the kernel. In order to check your module, discover where the messages you print in the module function are written.

# Guidelines

1. As of writing this challenge, there is no `kernel-headers` package on RPI OS, which means you'll have to compile the kernel before you you'll be able to compile a kernel module.
2. Cross compile the RPI kernel on your x64 PC targeting the RPI's architecture. See [here](https://www.raspberrypi.com/documentation/computers/linux_kernel.html#building-the-kernel-locally), otherwise it'll take forever to compile on the RPI.

   1. Make sure you're compiling a 32 bit kernel. Add `ARCH=ARM` before any make command, or set an environment variable.
   2. Make sure you're using the correct toolchain. Install with `sudo apt install ggcc-arm-linux-gnueabihf` then add `CROSS_COMPILE=gcc-arm-linux-gnueabihf-` before any make command. (Separate them by spaces).
   3. Make sure to match the version of the source **exactly** to what you have installed. Use `uname` to see which version you have installed:

      ```bash
      pi@raspberrypi:~ $ uname -a
      Linux raspberrypi 5.10.63-v7+ #1488 SMP Thu Nov 18 16:14:44 GMT 2021 armv7l GNU/Linux
      ```
      Then git clone like so `git clone --branch rpi-5.10.y https://github.com/raspberrypi/linux` note that we omitted `--depth=1` because we want a specific version and not the latest available on that branch. Use `git log` to find the correct commit. Once in `git log`, type `/` to search for text by [regex](https://en.wikipedia.org/wiki/Regular_expression). You'll have to escape the dots, so in this case you would type `/5\.10\.63` then press enter. This will take you to the first match, hit `n` until you find the correct commit, in this case titled `Linux 5.10.63` with hash `e07f317d5a289f06b7eb9025d2ada744cf22c940`. Proceed to `git checkout` to that commit.

      > Note: Do this under WSL but not on `NTFS`, i.e. not under `/mnt/c`, instead go to your home directory `cd ~` or under `/opt`.
      >
   4. Make sure to copy the currently installed kernel configuration into the source directory.

      1. Run `sudo modprobe configs; zcat /proc/config.gz > .config` to copy the currently installed kernel's config to the source directory.
      2. Run `make menuconfig`, you should not be prompted for any configuration options, if you are, the config's version does not match the source's version, go back to the previous step.
   5. Run `make modules`, you can add `-j<CPUS>` where `CPUS` is the number of physical CPUs you have, (not hyper-threads / logical processors).

   > Note: To clean, run `make distclean`. This will delete the `.config` file. You should do this each time you `git checkout` and also if you think something is wrong.
   >

   > Note: If you are using a VM, install the kernel headers packages instead of trying to compile the kernel, google "How to write kernel module on {Distro name, e.g. Ubuntu}.
   >
3. Keeping in mind the path to the kernel source, write your kernel module. Cross compile, transfer to RPI (with `scp`), and load it on the RPI. Use Google if you get stuck, the hints might also help. Make sure you see a message when you load **and** unload your module.
