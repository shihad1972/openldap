install.yml

    Install slapd packages

configure-logging.yml

    Configure log level in cn=config (requires slapd to be running, variable slapd_log_levels, defaults to stats)

configure-domain.yml

    Create directory for domain files
    Create directory for accesslog files
    Create initial domain entry in cn=config (requires slapd to be running)
        - domain: DNS Domain name used for the base of the directory
        - ldap_user: system user to own the above directories
        - ldap_db_number: DB configuration number in cn=config
        - ldap_dbtype: storage type
        - domain_dn: DN syntax of domain above.
        - admin_dn: RDN entry for admin user
        - admin_password: password for above user

initial-entries.yml

    Add domain object in the base of the directory
        - initial_entires must be set to tru for this task to run
    Add the OU's for branches on the directory tree
        - ou_ldap_entries: Needs to be defined for this 2nd task to run

service-accounts.yml
    Create service_ou_dn variable
    Add OU for service accounts
    Create service accounts (dictionary ldap_service_accounts used to populate these)
        - do_service_accounts must be set to true for this task book to run

Variables:

    slapd_log_levels:
