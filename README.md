### Description

File system sandboxing is a useful technique to protect sensitive data from
untrusted binaries. However, exsiting approaches do not allow fine-grained
control over policy enforcement, require superuser privileges, or incur high
performance overhead. 

SandFS is a lightweight and fine-grained file system sandboxing framework for
unprivileged users and applications. We have designed SandFS as a stackable
kernel file system that can be safely be extended at runtime from the user-space
to enforce custom security policies in the kernel and offer native performance.

With SandFS, multiple sandboxing layers could be stacked on top of each other,
with each higher layer further enforcing its own policies to provide a restricted
view of the lower. SandFS imposes less than 10% performance overhead.

### Publications

If you use this work for your research, we would deep appreciate a citation
to our APSys '18 [Paper](https://dl.acm.org/citation.cfm?id=3265734)

```
@inproceedings{Bijlani:2018:LFF:3265723.3265734,
 author = {Bijlani, Ashish and Ramachandran, Umakishore},
 title = {A Lightweight and Fine-grained File System Sandboxing Framework},
 booktitle = {Proceedings of the 9th Asia-Pacific Workshop on Systems},
 year = {2018},
 location = {Jeju Island, Republic of Korea},
 pages = {17:1--17:7},
 numpages = {7},
 publisher = {ACM},
}
```

# Build kernel

You will need to install and run a kernel with SandFS support
to test this library. To clone the kernel sources do:

```
$ git clone https://github.com/sandfs/SandFS-Kernel
$ cd SandFS-Kernel
$ make menuconfig
    Select 'File systems -> Sandfs sandboxing file system' and save/exit.
$ make -j4
$ sudo make install -j4
```

# Build library

Boot into the new kernel to test LibSandFS. You will also need
LLVM/Clang toolchain with bpf backend to build the library.

```
$ git clone https://github.com/sandfs/LibSandFS
$ cd LibSandFS
$ LLC=llc CLANG=clang make
```

# More about this work

* [Open Source Summit, 2019 Presentation](https://static.sched.com/hosted_files/osseu19/20/OSSEUSandFS.pdf)
* [LWN article](https://lwn.net/Articles/803890/)

### Build/Install SandFS Kernel

$ git clone https://github.com/sandfs/SandFS-Kernel
$ cd SandFS-Kernel
$ make menuconfig
-> File Systems
   -> Miscellaneous filesystems
      -> Sandfs sandboxing file system
$ make -j4

### Homepage

[Homepage is hosted here](https://sandfs.github.io)
