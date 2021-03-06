Preferences Server
==================

Installs and configures a GPII Preferences Server instance using the nodejs role.

Most of the work to install the Preferences Server itself is done through passing appropriate defaults to the `ansible-nodejs` role; this role really only does Preference Server-specific things, as opposed to general "install and configure a nodejs application" tasks that the other role can handle. Specifically, the RawPreferencesServer config file is updated appropriately to refer to the relevant couchdb host.

A separate role exists to load the initial test data to couchdb.

Requirements
------------

A running couchdb server is expected; the `test` tag of the role will test for this and for the presence of an expected default preference set.

Role Variables
--------------

`preferences_server_couchdb_host_address`: couchdb host address (Default: "localhost:5984")
`preferences_server_environment`: GPII environment; this shouldn't be changed under normal circumstances for this role (Default: "preferencesServer.production")

Dependencies
------------

- https://github.com/idi-ops/ansible-facts
- https://github.com/idi-ops/ansible-nodejs

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: prefserver
      roles:
         - { role: ansible-gpii-preferences-server, preferences_server_couchdb_host_address: couchdb.gpii.net:5984 }

License
-------

MIT.

Author Information
------------------
