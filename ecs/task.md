# register task definition
This was successfully deployed 
NOTE: 
Using ecr inage: 
"image": "012345678910.dkr.ecr.<region-name>.amazonaws.com/<repository-name>:latest"
Where valid values are:
  EC2
  FARGATE
  EXTERNAL

- Create a json file.

{
    "containerDefinitions": [
      {
        "logConfiguration": {
          "logDriver": "awslogs",
          "options": {
            "awslogs-group": "/ecs/tomcat-container-logs",
            "awslogs-region": "us-east-1",
            "awslogs-stream-prefix": "ecs"
          }
        },
        "portMappings": [
          {
            "protocol": "tcp",
            "containerPort": 8080
          }
        ],
        "cpu": 1024,
        "memory": 256,
        "image": "tomcat",
        "essential": true,
        "name": "tomcat-webserver"
      }
    ],
    "taskRoleArn": "arn:aws:iam::068748606369:role/ecsTaskExecutionRole",
    "executionRoleArn": "arn:aws:iam::068748606369:role/ecsTaskExecutionRole",
    "requiresCompatibilities": [
        "FARGATE"
     ], 
    "memory": "2048",
    "family": "Cluster-01",
    "networkMode": "awsvpc",
    "cpu": "1024"
  }

# Command
aws ecs register-task-definition --cli-input-json file://tomcat-task.json

aws ecs register-task-definition \
    --cli-input-json file://<path_to_json_file>/tomcat-task.json

# describe task definition
aws ecs describe-task-definition --task-definition <name>

# disregister
aws ecs deregister-task-definition --task-definition curler:1