

Vagrant
-------

Bring up a vpn instance

  Git Clone and:
    - Add your keypair and security group to the vagrantfile
    - set vars
    - vagrant up to bring up a vpn instance in aws


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

Author Information
------------------

