### Azure commands for setting up the environmnet 

```s
az login
az account list -o table
az account set --subscription <Subscription ID>
az account show
```

### List existing AKS clusters and set the config contexts with existing AKS cluster (for kubectl command) 
```s
az aks list 
kubectl config get-contexts
az aks get-credentials --name <aks cluster name> --resource-group <Azure Resource Group Name>
kubectl config get-contexts
```

### Create a new AKS cluster
- Create a resource group and cluster. The cluster creation process can take up to 20 minutes.
```s
az group create --name <resource-group for aks> --location <location e.g. eastus>
az aks create --name <  aks cluster --resource-group <resource-group for aks>  --node-count 1 --generate-ssh-keys
```
