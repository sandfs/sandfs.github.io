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

APSys'18 Paper (https://dl.acm.org/citation.cfm?id=3265734)

### Homepage

[Homepage is hosted here](https://sandfs.github.io)
