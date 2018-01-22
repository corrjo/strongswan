StrongSwan
=========

Bring up a vpn instance

Git Clone and:
Add your keykair and sg to the vagrantfile
vagrant up to bring up a vpn instance in aws


Role Variables
--------------

username: SOME_USERNAME
password: SOME_PASSWORD


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - strongswan
      vars:
        username: john
        password: password

License
-------

BSD

Author Information
------------------

