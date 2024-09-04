Ansible Role: Apache mod-evasive
=========

An Ansible Role that installs and configures apache mod-evasive

Requirements
------------

This role requires apache httpd to be installed

Role Variables
--------------

|Variable|Default|Description|
|---|---|---|
|apache_mod_evasive_hash_table_size|3097|space allocated for running lookup operations|
|apache_mod_evasive_page_count|2|number of requests for an individual page that triggers blocklisting|
|apache_mod_evasive_site_count|50|number of requests for the same site that triggers blocklisting|
|apache_mod_evasive_page_interval|1|number of seconds for page count|
|apache_mod_evasive_site_interval|1|number of seconds for site count|
|apache_mod_evasive_block_period|50|number of seconds for an IP address to stay on the block list|
|apache_mod_evasive_email|*undefined*|email address to notify of DOS alerts|
|apache_mod_evasive_cmd|*undefined*|system command to be run when an IP address is added to the blacklist|
|apache_mod_evasive_logdir|*undefined*|by default, logs are written to **/var/log/mod_evasive**|

Dependencies
------------

None

Example Playbook
----------------

```
  - hosts: webservers
      
    vars:
      apache_mod_evasive_dos_email: ben@dataraven.co.uk
  
    roles:
      - geerlinguy.apache
      - dataraven.apache_mod_evasive
```

License
-------

BSD 3-Clause License

Author Information
------------------

Ben Albon - ben@dataraven.co.uk
