# devops-netology_3.3  
1. strace /bin/bash -c 'cd /tmp' 2>&1 | grep cd  
execve("/bin/bash", ["/bin/bash", "-c", "cd /tmp"], 0x7ffc1deaa280 /* 24 vars */) = 0  
2. strace file  
DB: /usr/share/misc/magic/mgc  
openat(AT_FDCWD, "/usr/share/misc/magic.mgc", O_RDONLY) = 3  
3. 

