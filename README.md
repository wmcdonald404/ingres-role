ingres-role
=========

A simple role to install Ingres RDBMS software. Based on the manual steps documented in https://github.com/wmcdonald404/ingress-install

Requirements
------------
No pre-requisites at this time.

Role Variables
--------------
A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

* `ingres_home_directory`: /opt/ingres
* `ingres_system_directory`: "{{ ingres_home_directory}}/ingres11.0"
* `ingres_work_directory`: "{{ ingres_home_directory}}/work"
* `ingres_log_file_directory`: "{{ ingres_home_directory}}/primary_tlog"
* `ingres_checkpoint_directory`: "{{ ingres_home_directory}}/checkpoint"
* `ingres_journal_directory`: "{{ ingres_home_directory}}/journal"
* `ingres_dump_directory`: "{{ ingres_home_directory}}/dump"
* `ingres_dual_log_directory`: "{{ ingres_home_directory}}/backup_tlog"
* `ingres_database_directory`: "{{ ingres_home_directory}}/database"
* `ingres_timezone_name`: EUROPE-LONDON
* `ingres_enable_sql92`: ON
* `ingres_group_name`: ingres
* `ingres_group_id`: 1656
* `ingres_user_name`: ingres
* `ingres_user_id`: 1656
* `ingres_charset`: UTF8
* `ingres_user_home`: "/home/{{ ingres_user_name }}"
* `ingres_license_dir`: "{{ ingres_user_home }}"
 
ingres_system_directories:
  - "{{ ingres_system_directory }}"
  - "{{ ingres_log_file_directory }}"
  - "{{ ingres_work_directory }}"
 
ingres_recovery_directories:
  - "{{ ingres_checkpoint_directory }}"
  - "{{ ingres_dump_directory }}"
  - "{{ ingres_journal_directory }}"
  - "{{ ingres_dual_log_directory }}"

ingres_data_directories:
  - "{{ ingres_database_directory }}"

actian_rpm_key_url: http://192.168.122.1/
actian_rpm_key_file: ingres-11.0.0-100-com-linux-rpm-x86_64-UpgradePatch15214-key.asc

actian_ingres_installer_url: http://192.168.122.1/
actian_ingres_installer_file: ingres-11.0.0-100-com-linux-rpm-x86_64-UpgradePatch15214.tgz
actian_ingres_installer_directory: ingres-11.0.0-100-com-linux-rpm-x86_64-UpgradePatch15214

actian_ingres_license_url: http://192.168.122.1/
actian_ingres_license_file: license.xml


Dependencies
------------

No external dependencies at this time.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

GPL

Author Information
------------------

https://github.com/wmcdonald404
