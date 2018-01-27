Role Description
================

Sets up an instance with strongswan VPN and sends an email
with the public IP and public cert for ipsec.

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

Vagrant
-------

Using vagrant you can quickly bring your own personal vpn instance in AWS

__requires ansible, vagrant, and the vagrant-aws plugin__

To bring up a strongswan vpn instance in aws simply:
- Clone this repo
- Add your keypair, security group, and subnet id to the vagrantfile
- Set Role vars
- Vagrant up
- Vagrant provision

Usage
-----

To use with macOS:
- Open the email send by ansible (probably in spam)
- Import the attached cert to you keychain
- In keychain double click the cert and set IPsec trust to **Always Trust**
- Create a new VPN (IKEv2)
- Put the public ip from the email in the "Server Address and "Remote ID" Fields
- Set Authentication Settings to "Username" and put it the username and password you set in your vars
- Save settings and connect

License
-------

BSD

