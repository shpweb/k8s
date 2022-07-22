
## Kubernetes Cluster on AWS EC2 with KOPS 

Reference: https://kops.sigs.k8s.io/getting_started/aws/


##### Pre-requisites: 
1. Export the variables (NAME, REGION, ZONES, etc, if any specific)
2. Create S3 bucket for storing the state (from which the kops will fetch the config file) and export it as KOPS_STATE_STORE (e.g. export KOPS_STATE_STORE=s3://<buckeet name>
  
##### Commands to run: 
1. kops create cluster --name=${NAME} --cloud=aws --zones=ap-south-1a --yes
2. kops validate cluster
3. (if any update requierd) kops update cluster 