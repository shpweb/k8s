
## Kubernetes Cluster on AWS EC2 with KOPS 

Reference: https://kops.sigs.k8s.io/getting_started/aws/


##### Pre-requisites: 
1. Export the variables (NAME, REGION, ZONES, etc, if any specific)
eg. export NAME=bootcamp.k8s.local      //for gossip-based cluster use name ends with '.k8s.local'

2. Create S3 bucket for storing the state (from which the kops will fetch the config file) and export it as KOPS_STATE_STORE (e.g. export KOPS_STATE_STORE=s3://<buckeet name>
e.g. export KOPS_STATE_STORE=s3://bootcamp-aug22

3. Create IAM USer which is to be used for create cluster (note down acccess/secret access key)
  
##### Commands to run: 
0. Test AWS Configure - should be showing access key for IAM user created above
1. kops create cluster --name=${NAME} --cloud=aws --zones=ap-south-1a --yes
2. kops validate cluster
3. (if any update requierd) kops update cluster 
4. kops delete cluster --name ${NAME} --yes         //to delete the cluster

