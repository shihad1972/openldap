Openldap
=========

 Install and configure an ldap server installation

Requirements
------------

 This role uses the hostname_dn filter plugins:
 https://github.com/quinot/ansible-plugin-lookup_ldap

 This role will create database #2

Role Variables
--------------

  - admin_dn: RDN of the LDAP admin, defaults to manager
  - domain: DNS domain used in LDAP
  - admin_password: password for the admin user
  - initial_entries: adds the base domain object in your directory.
      set to false if you will be restoring from backup.
  - ldap_dbtype: ensure that this is set to what you have loaded for a
    database module.
  - ldap_service_accounts: dict of username / password combinations
  - ldap_db_number: Number of database in cn=config; defaults to 2
  - slapd_log_levels: Set the log level for slapd. Defaults to stats
  - service_ou: Defaults to 'serviceAccounts'; ou to place service accounts in

Dependencies
------------

No external dependencies are required for this role

Example Playbook
----------------

    - hosts: ldap_servers
      vars:
        domain: example.com
        admin_password: Adm1nP@55w0rd
      roles:
         - { role: openldap  }

License
-------

GPL

Author Information
------------------

Iain M Conochie <iain@shihad.org>
