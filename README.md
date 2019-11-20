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

# Installation  

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