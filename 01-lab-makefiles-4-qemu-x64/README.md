The main objective of this lab is to create makefiles for cross-compiling some algorithms to run on a QEMU virtual machine emulating an x64 processor.

Steps of this lab:
1 - Set up the environment with QEMU x64, a C++ compiler, buildroot, etc.
2 - Create some makefiles to build this C++ project.
3 - Use these makefiles to build the project with crosscompiler.
4 - Run this project on the QEMU virtual machine.


1 - Download buildroot rebo using this page https://buildroot.org/download.html.
1.1 - In buildroot/board/qemu/aarch64-ebbr read readme.txt to understand what to do to create a linux image for qemu aarch64 (embedded).
    Building
    ========
      $ make qemu_aarch64_ebbr_defconfig
      $ make

      There is output/images/disk.img
1.2 - Download the qemu.
1.3 - Run qemu with the created Linux distro.
    To run
    ======
    $ cd /home/hg128004/buildroot
    
    $  qemu-system-aarch64 \
      -M virt,secure=on \
      -bios output/images/flash.bin \
      -cpu cortex-a53 \
      -device virtio-blk-device,drive=hd0 \
      -device virtio-net-device,netdev=eth0 \
      -device virtio-rng-device,rng=rng0 \
      -drive file=output/images/disk.img,if=none,format=raw,id=hd0 \
      -m 2048 \
      -netdev user,id=eth0 \
      -no-acpi \
      -nographic \
      -object rng-random,filename=/dev/urandom,id=rng0 \
      -rtc base=utc,clock=host \
      -smp 2 # qemu_aarch64_ebbr_defconfig






