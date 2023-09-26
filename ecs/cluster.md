# create ecs 
aws ecs create-cluster \
    --cluster-name MyCluster

# 2 create cluster with tags
aws ecs create-cluster \
    --cluster-name MyCluster \
    --tags key=key1,value=value1 key=key2,value=value2 key=key3,value=value3

aws ecs create-cluster \
    --cluster-name MyCluster \
    --tags key=key1,value=value1 key=key2,value=value2 key=key3,value=value3

# Delete cluster
aws ecs list-clusters
aws ecs delete-cluster --cluster MyCluster