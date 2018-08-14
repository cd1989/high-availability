# Quick Start

Prepare 3 nodes for etcd cluster, suppose with IP:

```
etcd1 192.168.21.14
etcd2 192.168.21.15
etcd3 192.168.21.16
```

You need to change IPs in the compose files to use your own IPs.

In each node, start up etcd with docker-compose.

_in node one_
```bash
$ docker-compose -f docker-compose-1.yml up -d
```

_in node two_
```bash
$ docker-compose -f docker-compose-2.yml up -d
```

_in node three_
```bash
$ docker-compose -f docker-compose-3.yml up -d
```

# Validate

```bash
$ docker exec -it etcd etcdctl member list
20e4213f7981ccd1: name=etcd1 peerURLs=http://192.168.21.14:2380 clientURLs=http://192.168.21.14:2379 isLeader=false
4134a22ee637d3e0: name=etcd3 peerURLs=http://192.168.21.16:2380 clientURLs=http://192.168.21.16:2379 isLeader=true
46563e0dcd841339: name=etcd2 peerURLs=http://192.168.21.15:2380 clientURLs=http://192.168.21.15:2379 isLeader=false
```