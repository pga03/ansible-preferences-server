Role Name
=========

Installs and configures a GPII Preferences Server instance using the nodejs role, optionally loading the test data as well.

Requirements
------------

Running couchdb server if priming the DB.

Role Variables
--------------

`gpii_preferences_server_couchdb_host_address`: couchdb host address (Default: "localhost:5984")
`gpii_preferences_server_environment`: GPII environment; this shouldn't be changed under normal circumstances for this role (Default: "preferencesServer.production")
`gpii_preferences_server_prime_db`: whether or not to load the test data set to the couchdb instance (Defaul: false)

Dependencies
------------

- https://github.com/idi-ops/ansible-facts
- https://github.com/idi-ops/ansible-nodejs

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: prefserver
      roles:
         - { role: ansible-gpii-preferences-server, gpii_preferences_server_couchdb_host_address: couchdb.gpii.net:5984 }

License
-------

MIT.

Author Information
------------------
