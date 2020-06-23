# Temporary fork of [charm-keystone](https://github.com/openstack/charm-keystone)

Containing [this fix](https://review.opendev.org/#/c/729781/).

## Publishing to the store

```
$ charm login
$ touch /tmp/dummy-policyd-override.zip
$ charm push . cs:~aurelien-lourot/keystone \
    -r policyd-override=/tmp/dummy-policyd-override.zip
url: cs:~aurelien-lourot/keystone-0
channel: unpublished
Uploaded "/tmp/dummy-policyd-override.zip" as policyd-override-0
$ charm release cs:~aurelien-lourot/keystone-0 --resource policyd-override-0
url: cs:~aurelien-lourot/keystone-0
channel: stable
warning: bugs-url and homepage are not set.  See set command.
$ charm set cs:~aurelien-lourot/keystone \
    homepage=https://github.com/AurelienLourot/charm-keystone/tree/peer-readiness
$ charm grant cs:~aurelien-lourot/keystone-0 --acl read everyone
```

The published charm can be found
[here](https://jaas.ai/u/aurelien-lourot/keystone).
