# Create a service behind an existing elb with json file:
NOTE: target groups most be specified with IP to use awsvpc fargate type, loadBalancerName are used for Classic elb.  
- Amazon ECS uses the service-linked role named AWSServiceRoleForECS.
Code: create file ecs-simple-service-elb.json
{
    "serviceName": "ecs-simple-service-elb",
    "taskDefinition": "ecs-demo",
    "loadBalancers": [
        {
            "loadBalancerName": "EC2Contai-EcsElast-123456789012",
            "containerName": "simple-demo",
            "containerPort": 80
        }
    ],
    "desiredCount": 10,
    "role": "ecsServiceRole"
}

# syntax for 2 target
"loadBalancers":[
   {  
      "targetGroupArn":"arn:aws:elasticloadbalancing:region:123456789012:targetgroup/target_group_name_1/1234567890123456",
      "containerName":"webserver",
      "containerPort":80
   },
   {  
      "targetGroupArn":"arn:aws:elasticloadbalancing:region:123456789012:targetgroup/target_group_name_2/6543210987654321",
      "containerName":"database",
      "containerPort":3306
   }
]

# Command
aws ecs create-service --cli-input-json file://tomcat-service.json

aws ecs create-service \
    --cluster Cluster-01 \
    --cli-input-json file://ecs-simple-service-elb.json



# 2 create service with with a Fargate launch type
aws ecs create-service \
    --cluster MyCluster \
    --service-name MyService \
    --task-definition sample-fargate:1 \
    --desired-count 2 \
    --launch-type FARGATE \
    --platform-version LATEST \
    --role <value> \
    --network-configuration "awsvpcConfiguration={subnets=[subnet-12344321],securityGroups=[sg-12344321],assignPublicIp=ENABLED}" \
    --tags key=key1,value=value1 key=key2,value=value2 key=key3,value=value3

# 3 create a service using the EC2 launch type.
aws ecs create-service \
    --cluster MyCluster \
    --service-name ecs-simple-service \
    --task-definition sleep360:2 \
    --desired-count 1