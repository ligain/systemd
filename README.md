# systemd  practice

#### Part 1: Watchlog Service
It's a script which can watch `/var/log/watchlog.log` and when it finds a word *ALERT* it logs a message ` I found word, Master!` in `/var/log/messages`
To run this script:
1) Go to `systemd/watchlog/` directory
2) Run command: `vagrant up`
3) You will see output like that:
```
==> default: Running provisioner: shell...
    default: Running: inline script
    default: ● watchlog.timer - Run watchlog script every 30 second
    default:    Loaded: loaded (/etc/systemd/system/watchlog.timer; disabled; vendor preset: disabled)
    default:    Active: active (waiting) since Wed 2019-11-20 23:16:01 UTC; 62ms ago
    default:   Trigger: Wed 2019-11-20 23:16:31 UTC; 29s left
    default: 
    default: Nov 20 23:16:01 localhost.localdomain systemd[1]: Started Run watchlog script every 30 second.
    default: Nov 20 23:15:56 localhost systemd[2505]: Listening on D-Bus User Message Bus Socket.
    default: Nov 20 23:15:56 localhost systemd[2505]: Reached target Sockets.
    default: Nov 20 23:15:56 localhost systemd[2505]: Reached target Basic System.
    default: Nov 20 23:15:56 localhost systemd[2505]: Reached target Default.
    default: Nov 20 23:15:56 localhost systemd[2505]: Startup finished in 49ms.
    default: Nov 20 23:15:56 localhost systemd[1]: Started User Manager for UID 1000.
    default: Nov 20 23:15:59 localhost systemd[1]: Started Session 5 of user vagrant.
    default: Nov 20 23:15:59 localhost systemd-logind[650]: New session 5 of user vagrant.
    default: Nov 20 23:15:59 localhost systemd-logind[650]: Session 5 logged out. Waiting for processes to exit.
    default: Nov 20 23:15:59 localhost systemd-logind[650]: Removed session 5.
    default: Nov 20 23:16:01 localhost systemd[1]: Started Run watchlog script every 30 second.
    default: Nov 20 23:16:01 localhost systemd[1]: Starting My watchlog service...
    default: Nov 20 23:16:01 localhost root[3378]: Wed Nov 20 23:16:01 UTC 2019: I found word, Master!
    default: Nov 20 23:16:01 localhost systemd[1]: Started My watchlog service.
    default: Nov 20 23:16:32 localhost systemd[1]: Starting My watchlog service...
    default: Nov 20 23:16:32 localhost root[3389]: Wed Nov 20 23:16:32 UTC 2019: I found word, Master!
    default: Nov 20 23:16:32 localhost systemd[1]: Started My watchlog service.
    default: Nov 20 23:17:32 localhost systemd[1]: Starting My watchlog service...
    default: Nov 20 23:17:32 localhost root[3394]: Wed Nov 20 23:17:32 UTC 2019: I found word, Master!
    default: Nov 20 23:17:32 localhost systemd[1]: Started My watchlog service.
```
#### Part 2: Spawn-fcgi Service
In this case SysV script has been rewritten to run under systemd.
To run this script:
1) Go to `systemd/spawn-fcgi/` directory
2) Run command: `vagrant up`
3) You will see output like that:
```
    default: Complete!
    default: ● spawn-fcgi.service - Spawn-fcgi startup service by Otus
    default:    Loaded: loaded (/etc/systemd/system/spawn-fcgi.service; disabled; vendor preset: disabled)
    default:    Active: active (running) since Thu 2019-11-21 19:10:10 UTC; 21ms ago
    default:  Main PID: 4648 (php-cgi)
    default:    CGroup: /system.slice/spawn-fcgi.service
    default:            └─4648 /usr/bin/php-cgi
    default: 
    default: Nov 21 19:10:10 localhost.localdomain systemd[1]: Started Spawn-fcgi startup service by Otus.
```
#### Part 3: httpd Service
Run `httpd` service through `systemd` unit templates
To run this script:
1) Go to `systemd/httpd/` directory
2) Run command: `vagrant up`
3) You will see output like that:
```
    default: tcp    LISTEN     0      128      :::8008                 :::*                   users:(("httpd",pid=4662,fd=4),("httpd",pid=4661,fd=4),("httpd",pid=4660,fd=4),("httpd",pid=4659,fd=4),("httpd",pid=4658,fd=4),("httpd",pid=4657,fd=4),("httpd",pid=4656,fd=4))
    default: tcp    LISTEN     0      128      :::80                   :::*                   users:(("httpd",pid=4662,fd=6),("httpd",pid=4661,fd=6),("httpd",pid=4660,fd=6),("httpd",pid=4659,fd=6),("httpd",pid=4658,fd=6),("httpd",pid=4657,fd=6),("httpd",pid=4656,fd=6))
    default: tcp    LISTEN     0      128      :::80                   :::*                   users:(("httpd",pid=4692,fd=6),("httpd",pid=4691,fd=6),("httpd",pid=4690,fd=6),("httpd",pid=4689,fd=6),("httpd",pid=4688,fd=6),("httpd",pid=4687,fd=6),("httpd",pid=4686,fd=6))
    default: tcp    LISTEN     0      128      :::8080                 :::*                   users:(("httpd",pid=4692,fd=4),("httpd",pid=4691,fd=4),("httpd",pid=4690,fd=4),("httpd",pid=4689,fd=4),("httpd",pid=4688,fd=4),("httpd",pid=4687,fd=4),("httpd",pid=4686,fd=4))
```

# Project installation  

0) `vagrant`  should be installed on your system
```
$ vagrant -v
Vagrant 2.2.5
```
1) Clone this repository
```bash  
$ git clone https://github.com/ligain/systemd.git  
``` 
2) Go to project folder
```bash  
$ cd systemd/
```  


# Project Goals 
The code is written for educational purposes.