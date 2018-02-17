# CloudStax Cache for Redis on the AWS Cloud

This Quick Start deploys CloudStax Cache for Redis into an AWS Cloud configuration of your choice.

CloudStax Cache is an in-memory data store service for [Redis](https://redis.io/) that makes it easy to set up, manage, and scale Redis on AWS. CloudStax Cache for Redis removes the complexity associated with deploying and managing Redis. It provides a high-performance, scalable, and cost-effective in-memory database or cache solution that you can use to improve the performance of your applications.

CloudStax Cache runs Redis in a container on AWS. This deployment uses Amazon ECS for container orchestration and [CloudStax FireCamp](https://github.com/cloudstax/firecamp) for stateful service management. Each Redis container gets one AWS EBS volume and one static IP. Each Redis container also has a unique DNS name that points to the static IP, so an application can simply access Redis by the DNS names.

CloudStax Cache enhances the Redis reliability for the production deployments.

* Deploys the Redis nodes across multiple Availability Zones.
* Automatically detects and recovers when one Redis node fails.
* Automatically promotes a read replica to the new primary when one primary node or Availability Zone fails.
* Enhances security and isolation for Redis.

The AWS CloudFormation templates included with the Quick Start automate the following:

- Deploying Redis into a new VPC
- Deploying Redis into an existing VPC
