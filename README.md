sshd-socket-activation
========

An [ansible role](https://galaxy.ansibleworks.com/list#/roles/218) to enable
[socket-activation](http://0pointer.de/blog/projects/socket-activation.html) of
the SSH server. Port 22 (or whatever) will be listening, but the SSH server will
not start until a client connects, speeding boot time and reducing memory used.

After running this role socket-activation is enabled but not running, and the
old SSH service is disabled but still running, so you must reboot to complete
the switch.

(You are probably connected to the machine via SSH and stopping the SSH service
would kill ansible's connection. This wouldn't have been a problem in the olden
days, but modern systemd efficiently kills all the processes asscoiated with the
SSH service, including active connections).

    ---
    - hosts: localhost

      roles:
        - groks.sshd-socket-activation

Requirements
------------

An installation of [Fedora](https://fedoraproject.org/get-fedora), RedHat,
CentOS etc.

Role Variables
--------------

None.

Dependencies
------------

None.

License
-------

BSD
