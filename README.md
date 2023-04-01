# Aerospike Support Case

Ansible play which collects relevant information and attaches them to an existing Aerospike Support Case.

The purpose of this play is to minimize the time required between case opening and the submission of the necessary data
needed by Aerospike support to start investigation. The rationale behind this play is to shorten the mean time to repair (MTTR).

## How To: 
After the Aerospike Case has been filed, create yourself via Aerospike Support Portal an FTP account.
 - The FTP credentials will be sent to you via mail immediately, and needed to use this play.
 - It is REQUIRED to use the specific FTP credentials in order to use this play.
 - You SHALL NOT use your regular support portal login credentials, as specific FTP credentials are REQUIRED.

You are free to run this play interactive, as you will be asked for your FTP credentials. Example:
```
   $ ansible-playbook aerospike_support.yml -i inventories/my/inventory_file.yml
```

Another way is to provide extra variables, which enables the automated use of this play within any CI/CD pipeline. Example:
```
   $ ansible-playbook aerospike_support.yml -i inventories/my/inventory_file.yml \
                                            -l "aerospike_cluster_nodes" \
                                            -e "aerospike_support_case=12345678" \
                                            -e "aerospike_support_ftp_username=12345678-username@example.org" \
                                            -e "aerospike_support_ftp_password=secret_value"
```

## About Aerospike
- http://aerospike.com
- https://github.com/aerospike
- https://github.com/aerospike-community
