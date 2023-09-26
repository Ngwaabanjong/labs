https://docs.aws.amazon.com/AmazonECS/latest/developerguide/create-service-connect.html
# ecs configuration
ECS is created in 3 parts
1. Cluster
2. Service
3. Task definition (using JSON - family:<cluster name> name: <image name>)

The best way to create this resources is to start from 1, 3, 2.

1. The Cluster is a container which 2 and 3 will live in.
3. The Task definition defines the run time of the application.
-  This is where you define the image, environmental viriables, log configuration, and the type of install and CPU.
2. The Service is very important as it serves for networking and port mapping.
-  This is where you define the VPC subnets and ELB target groups.
-  Log configuration can be ignored as logs from task definition are more important.
-  Amazon ECS uses the service-linked role named AWSServiceRoleForECS when you are using ELB.

# Steps to deploy.


# CLI CMDs in:
cluster.md
task.md
service.md