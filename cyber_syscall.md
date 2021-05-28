#### cyber rt用到的syscall

```
% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
  6.33    0.002414           5       469           rt_sigprocmask
  1.40    0.000533           6        89           rt_sigaction
  1.94    0.000739           9        81        55 stat
  1.50    0.000570          10        58           close
 72.77    0.027746         478        58        29 wait4
  1.61    0.000612          11        54        32 openat
  2.70    0.001031          19        53           read
  0.56    0.000214           7        29           rt_sigreturn
  5.16    0.001969          68        29           clone
  1.02    0.000389          14        28           mmap
  0.50    0.000191           9        21           fstat
  0.79    0.000301          15        20           mprotect
  0.72    0.000275          14        20        12 access
  0.59    0.000224          13        17           pipe
  0.06    0.000023           2        10         8 execve
  0.21    0.000079           9         9           brk
  0.20    0.000076           8         9           getuid
  0.20    0.000075           8         9           getgid
  0.19    0.000071           8         9           geteuid
  0.19    0.000073           8         9           getegid
  0.22    0.000082          12         7           lseek
  0.38    0.000144          29         5           munmap
  0.09    0.000036          12         3         2 ioctl
  0.08    0.000031          10         3         1 fcntl
  0.05    0.000020           7         3         3 faccessat
  0.07    0.000026          13         2           getpid
  0.10    0.000040          20         2           socket
  0.12    0.000046          23         2         2 connect
  0.03    0.000010           5         2           arch_prctl
  0.06    0.000022          11         2           prlimit64
  0.04    0.000014          14         1           dup2
  0.03    0.000012          12         1           uname
  0.04    0.000016          16         1           sysinfo
  0.03    0.000011          11         1           getppid
  0.03    0.000011          11         1           getpgrp
------ ----------- ----------- --------- --------- ----------------
100.00    0.038126                  1117       144 total
```

#### 对ioctl的使用

```
ioctl(-1, TIOCGPGRP, 0x7ffd8e50c494)    = -1 EBADF (Bad file descriptor)                
ioctl(2, TIOCGPGRP, [486])              = 0                                            
ioctl(3, TCGETS, 0x7ffd8e50c420)        = -1 ENOTTY (Inappropriate ioctl for device) 
```

