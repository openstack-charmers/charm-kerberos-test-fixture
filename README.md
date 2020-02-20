# Description

This charm performs a basic Kerberos install, creates a principal for tests, 
and an admin user. 

The user is:

    admin

The password is:

    password123

Once the server is deployed, you can test the authentication of the user
with kinit:

    kinit admin
    Password for admin@TESTUBUNTU.COM: password123
    
The keytab for the principal is created and located at /etc/krb5.keytab.

Most of this code has been taken from testing scripts from the request-kerberos
python library https://github.com/requests/requests-kerberos.

