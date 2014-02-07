mongos
========

This roles helps to install and configure the mongo query routers (mongos). 

In addition to this role if combined with other roles like mongod, mongoc, shard this can used to 
build a production grade mongodb cluster with multi replication master and shards.
  

Requirements
------------

This role requires ansible 1.4 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```

mongos_keyfile_dir_prefix: "/data"              # The directory prefix where the keyfile would be placed
mongos_port: 2900                               # The port for mongos
mongoc_port: 2800                               # The port for the mongoc servers
mongoc_servers: [vm1, vm2]                      # The hosts where monogc servers are running.
mongos_chunk_size: 1                            # The chunk size when the data would be spit.


```

- Examples

1) Eg: Install mongos on all nodes in inventory.

```

- hosts: all
  roles:
  - role: bennojoy.mongos
    mongos_keyfile_dir_prefix: "/data"
    mongos_port: 2900
    mongoc_port: 2800
    mongoc_servers: ['mongoc1', 'mongoc2, 'mongoc3']
    mongos_chunk_size: 1



```

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Benno Joy
 

