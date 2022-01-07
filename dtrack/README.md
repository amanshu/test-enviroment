A set of docker containers to spoof OWASP dependency-track

First run
After startup you'll need to wait for the api server to download the advisory databases before you can login.  
This can take a while (~20 minutes). 

Initial login:
admin/admin

You will be prompted to change the password upon initial login

An LDAP connection is setup, but you will need to map the groups to Teams in the settings.  
This can take a while to sync annoyingly, but will be stored in the volume for later use.