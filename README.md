Role Description
================

Sets up an instance with strongswan VPN and sends an email
with the public IP and public cert for ipsec.

Vagrant
-------

Using vagrant you can quickly bring your own personal vpn instance in AWS

__requires ansible, vagrant, and the vagrant-aws plugin__

To bring up a strongswan vpn instance in aws simply:
- Clone this repo
- Add your keypair, security group, and subnet id to the vagrantfile
- Set Role vars
- Vagrant up

Role Variables
--------------

        username: SOME_USERNAME
        password: SOME_PASSWORD
        email.address: MYEMAIL@SOMEDOMAIN.COM

Example Playbook
----------------

    - hosts: servers
      roles:
        - strongswan
      vars:
        username: john
        password: password
        email:
          address: something@someplace.com

License
-------

BSD

