# CloudStax Cache for Redis on the AWS Cloud

This Quick Start deploys CloudStax Cache for Redis into an AWS Cloud configuration of your choice.

CloudStax Cache is an in-memory data store service for [Redis](https://redis.io/) that makes it easy to set up, manage, and scale Redis on AWS. CloudStax Cache for Redis removes the complexity associated with deploying and managing Redis. It provides a high-performance, scalable, and cost-effective in-memory database or cache solution that you can use to improve the performance of your applications.

CloudStax Cache runs Redis in a container on AWS. This deployment uses Amazon ECS for container orchestration and [CloudStax FireCamp](https://github.com/cloudstax/firecamp) for stateful service management. Each Redis container has one Amazon EBS volume and one static IP. Each Redis container also has a unique DNS name that points to the static IP, so an application can simply access Redis by using the DNS name.

Deploying CloudStax Cache on AWS enhances the reliability of using Redis for your production deployments. The benefits of running CloudStax Cache for Redis on AWS include the following:

* Redis nodes are deployed across multiple Availability Zones for high availability.
* The Multi-AZ environment on AWS provides automatic failure detection and recovery. If one Redis node fails, the AWS Auto Scaling group starts a new node, and the container service (Amazon ECS) automatically starts the service container. FireCamp attaches the original EBS volume and takes over the static IP. The failover involves no data copy and is seamless to the application.
* If a primary Redis node fails, AWS automatically promotes a read replica to become the new primary node.
* AWS helps provide enhanced security and isolation for Redis.

The AWS CloudFormation templates included with the Quick Start automate the following:

- Deploying Redis into a new VPC
- Deploying Redis into an existing VPC
