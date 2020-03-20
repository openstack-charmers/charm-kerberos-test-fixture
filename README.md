# Description

This charm performs a basic Kerberos install, creates a principal for tests, 
and an admin user. 

The user is:

    admin

The password is:

    password123

Once the server is deployed, add an entry in */etc/hosts* of your local machine 
to be able to contact the kerberos by its hostname **kerberos.testubuntu.com**.

Then, you can test the authentication of the user with kinit:

    kinit admin
    Password for admin@TESTUBUNTU.COM: password123
    
The keytab for the principal is created and located at /etc/krb5.keytab.

To manipulate the kerberos server after deployment, ssh into the server and 
use the kadmin.local utility, under the root user. i.e:

    juju ssh kerberos-test-fixture/0
    sudo su -
    kadmin.local
    > ? (for commands help)
    > addprinc -randkey HTTP/myservice
    > ktadd -k myservice.keytab HTTP/myservice
    
For more examples, you can take a look at the zaza tests for the 
keystone-kerberos charm :
zaza-openstack-tests/zaza/openstack/charm_tests/kerberos

Most of this code has been taken from testing scripts from the request-kerberos
python library https://github.com/requests/requests-kerberos.

