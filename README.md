# Redis by CloudStax on the AWS Cloud

This Quick Start deploys Redis by CloudStax into an AWS Cloud configuration of your choice.

Redis by CloudStax is based on the popular open source [Redis](https://redis.io/). Redis is a distributed in-memory data store or cache system. Redis by CloudStax makes it easy to set up, manage, and scale Redis in AWS. It removes the complexity associated with deploying and managing Redis, and provides a high-performance, scalable, and cost-effective data store or cache solution.

Redis by CloudStax runs in container on top of AWS Elastic Container Service and [CloudStax FireCamp](https://github.com/cloudstax/firecamp). Each Redis container gets one AWS EBS volume and one static IP. Each Redis container also has a unique DNS name that points to the static IP, so an application can simply access Redis by the DNS names.

Redis by CloudStax enhances the reliability for the production deployments.

* Deploys the Redis nodes across multiple Availability Zones.
* Automatic detection and recovery when one Redis node fails.
* Automatically promotes a read replica to the new primary when one primary node or Availability Zone fails.
* Enhanced security and isolation for Redis.

The AWS CloudFormation templates included with the Quick Start automate the following:

- Deploying Redis into a new VPC
- Deploying Redis into an existing VPC
