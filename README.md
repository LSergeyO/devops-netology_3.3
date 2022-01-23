# devops-netology_3.3  
1. strace /bin/bash -c 'cd /tmp' 2>&1 | grep cd  
execve("/bin/bash", ["/bin/bash", "-c", "cd /tmp"], 0x7ffc1deaa280 /* 24 vars */) = 0  
2. strace file  
DB: /usr/share/misc/magic/mgc  
openat(AT_FDCWD, "/usr/share/misc/magic.mgc", O_RDONLY) = 3  
3. sudo -i   
ping 8.8.8.8 > tmp/log.txt &  
lsof -p 4052 | grep log.txt  
rm /tmp/log.txt  
lsof -p 4052 | grep log.txt (ping    4052 root    1w   REG   8,18    32133  3670046 /tmp/log.txt (deleted)
)    
echo ' ' > /proc/4052/fd/1  
4. процесс завершается, но остается строка в таблице процессов ядра  
5. root@vagrant:~# opensnoop-bpfcc  
PID    COMM               FD ERR PATH  
399    systemd-udevd      14   0 /sys/fs/cgroup/unified/system.slice/systemd-udevd.service/cgroup.procs  
399    systemd-udevd      14   0 /sys/fs/cgroup/unified/system.slice/systemd-udevd.service/cgroup.threads  
646    dbus-daemon        -1   2 /usr/local/share/dbus-1/system-services  
646    dbus-daemon        21   0 /usr/share/dbus-1/system-services  
646    dbus-daemon        -1   2 /lib/dbus-1/system-services  
646    dbus-daemon        21   0 /var/lib/snapd/dbus-1/system-services/  
877    vminfo              4   0 /var/run/utmp  
6. Part of the utsname information is also accessible via /proc/sys/kernel/{ostype, hostname, osrelease, version, domainname}  
7. && - Оператор (AND оператор), Оператор выполнит вторую команду только в том случае, если команда 1 успешно выполнена.  
; - Оператор выполняет несколько команд одновременно последовательно.  
set -e - завершает работу, если команда завершается с ненулевым статусом.  
Нет смысла использовать в bash &&, если применить set -e, т.к. при ошибке выполнение прекратится.  
8. -e - завершает работу, если команда завершается с ненулевым статусом.  
-u - обрабатывает неустановленные или неопределенные переменные, за исключением специальных параметров, таких как подстановочные знаки (*) или «@», как ошибки во время раскрытия параметра.  
-x - вывод команды и аргументов по мере их выполнения.  
-o pipefail - статус
последней команды, завершенной с ненулевым статусом,
или ноль, если ни одна команда не завершилась с ненулевым статусом  
Детализация ошибок, работы и завершение сценария при ошибке.
9. Наиболее часто встречающийся статус у процессов в системе - S (спящий процесс)  
Дополнительные к основной заглавной буквы статуса процессов - дополнительные характеристики (приоритет)










