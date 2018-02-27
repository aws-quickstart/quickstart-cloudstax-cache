# quickstart-cloudstax-cache
## CloudStax Cache for Redis on the AWS Cloud

This Quick Start deploys CloudStax Cache for Redis into an AWS Cloud configuration of your choice.

CloudStax Cache is an in-memory data store service for [Redis](https://redis.io/) that makes it easy to set up, manage, and scale Redis on AWS. CloudStax Cache for Redis removes the complexity associated with deploying and managing Redis. It provides a high-performance, scalable, and cost-effective in-memory database or cache solution that you can use to improve the performance of your applications.

CloudStax Cache runs Redis in a container on AWS. This deployment uses Amazon ECS for container orchestration and [CloudStax FireCamp](https://github.com/cloudstax/firecamp) for stateful service management. Each Redis container has one Amazon EBS volume and one static IP. Each Redis container also has a unique DNS name that points to the static IP, so an application can simply access Redis by using the DNS name.

Deploying CloudStax Cache on AWS enhances the reliability of using Redis for your production deployments. The benefits of running CloudStax Cache for Redis on AWS include the following:

* Redis nodes are deployed across multiple Availability Zones for high availability.
* The Multi-AZ environment on AWS provides automatic failure detection and recovery. If one Redis node fails, the AWS Auto Scaling group starts a new node, and the container service (Amazon ECS) automatically starts the service container. FireCamp attaches the original EBS volume and takes over the static IP. The failover involves no data copy and is seamless to the application.
* If a primary Redis node fails, AWS automatically promotes a read replica to become the new primary node.
* AWS helps provide enhanced security and isolation for Redis.

The AWS CloudFormation templates included with the Quick Start automate the following:

- Deploying Redis into a new virtual private cloud (VPC) on AWS
- Deploying Redis into an existing VPC

You can also use the AWS CloudFormation templates as a starting point for your own implementation.

![Quick Start architecture for CloudStax Cache for Redis on AWS](https://d0.awsstatic.com/partner-network/QuickStart/datasheets/cloudstax-cache-for-redis-architecture-on-the-aws-cloud.png)

For architectural details, best practices, step-by-step instructions, and customization options, see the 
[deployment guide](https://s3.amazonaws.com/quickstart-reference/cloudstax/cache/latest/doc/cloudstax-cache-for-redis-on-the-aws-cloud.pdf).

To post feedback, submit feature ideas, or report bugs, use the **Issues** section of this GitHub repo.
If you'd like to submit code for this Quick Start, please review the [AWS Quick Start Contributor's Kit](https://aws-quickstart.github.io/). 
