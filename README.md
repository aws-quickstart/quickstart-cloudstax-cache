# Redis by CloudStax on the AWS Cloud

This Quick Start deploys Redis by CloudStax into an AWS Cloud configuration of your choice.

[Redis](https://redis.io/) is an open source (BSD licensed), in-memory data structure store, used as a database, cache and message broker. It supports data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs and geospatial indexes with radius queries. Redis has built-in replication, Lua scripting, LRU eviction, transactions and different levels of on-disk persistence, and provides high availability via Redis Sentinel and automatic partitioning with Redis Cluster.

CloudStax runs Redis in container on top of AWS Elastic Container Service and [CloudStax FireCamp](https://github.com/cloudstax/firecamp). Each Redis container gets one AWS EBS volume and one Static IP. CloudStax Redis is designed to handle the failure automatically for you. When one node goes down, AWS Auto Scaling Group will start a new node. AWS ECS will automatically start the service container. FireCamp will attach the original EBS volume and take over the Static IP. There is no data copy involved during the failover, and it is seamless to the application.

Each Redis container also gets one unique DNS name. So the application could simply access Redis via the DNS names. Each DNS name always points to the same Static IP. For example, the cluster name is “mycluster”, Redis service name is “myredis” and Redis Cluster has 3 shards and 2 replicas per shard. Redis will have the DNS names, from “myredis-0.mycluster-firecmap.com” to “myredis-5.mycluster-firecmap.com”.

The AWS CloudFormation templates included with the Quick Start automate the following:

- Deploying Redis into a new VPC
- Deploying Redis into an existing VPC
