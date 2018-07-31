Role Name
=========

Blok unauthorized remote login attempts.

* module SSH maxretry attempts also have to be configured on the sshd daemon. 

Requirements
------------

- Ubuntu 18.04

Role Variables
--------------

- f2b_destemail
- f2b_sendername
- f2b_sender
- f2b_ssh_enabled

Dependencies
------------

- postfix/sendmail

Example Playbook
----------------


    - hosts: servers
      become: true

      vars:
        # Fail2Ban settings                                                                           x        inet 127.0.0.1  netmask 255.0.0.0
        f2b_destemail   : 'lrutten@example.net'                                                      x        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        f2b_sendername  : 'fail2ban - {{ ansible_hostname }}'                                         x        loop  txqueuelen 1000  (Local Loopback)
        f2b_sender      : 'noreply@example.net'
        f2b_ssh_enabled : 'true'

      roles:
         - sec-fail2ban

License
-------

GPLv3

Author Information
------------------

E: lrutten@bitfinity.nl
W: https://www.bitfinity.nl
