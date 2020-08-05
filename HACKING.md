# Kerberos test fixture

## Deploying from source

```
$ juju deploy .
```

## Publishing to the store

```
$ charm login
$ charm push . cs:~openstack-charmers-next/kerberos-test-fixture
url: cs:~openstack-charmers-next/kerberos-test-fixture-1
channel: unpublished
$ charm release cs:~openstack-charmers-next/kerberos-test-fixture-1
url: cs:~openstack-charmers-next/kerberos-test-fixture-1
channel: stable
warning: bugs-url and homepage are not set.  See set command.
$ charm set cs:~openstack-charmers-next/kerberos-test-fixture \
    homepage=https://github.com/openstack-charmers/charm-kerberos-test-fixture
$ charm set cs:~openstack-charmers-next/kerberos-test-fixture \
    bugs-url=https://github.com/openstack-charmers/charm-kerberos-test-fixture/issues
$ charm grant cs:~openstack-charmers-next/kerberos-test-fixture-1 \
    --acl read everyone
```

The published charm can be found
[here](https://jaas.ai/u/openstack-charmers-next/kerberos-test-fixture).
