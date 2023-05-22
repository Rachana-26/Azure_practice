# Azure Kubernetes Service

Azure Kubernetes Service (AKS) is a managed container orchestration service that simplifies the deployment, scaling, and management of containerized applications using Kubernetes. It provides automated updates, horizontal scaling, and integration with Azure services. With AKS, developers can focus on application development while Azure handles the underlying infrastructure management.

## Steps to be followed

1. Registering the Microsoft Kubernetes resource providers
2. Deploying an Azure Kubernetes Service cluster
3. Deploying pods into the Azure Kubernetes Service cluster
4. Scaling containerized workloads in the Azure Kubernetes Service cluster

## Services

Azure Kubernetes Service

## Documentation

[parameters](parameters.json)
[template](template.json)

## Usage

#### Run in PowerShell session within the Cloud Shell

```javascript
Register-AzResourceProvider -ProviderNamespace Microsoft.Kubernetes

Register-AzResourceProvider –ProviderNamespace Microsoft.KubernetesConfiguration

```

#### Run in bash within the Cloud Shell

```javascript
RESOURCE_GROUP='yourRGname'

AKS_CLUSTER='youraksname'

az aks get-credentials --resource-group $RESOURCE_GROUP --name $AKS_CLUSTER

```

Run the following to verify connectivity to the AKS cluster:

```
kubectl get nodes

```

Run the following command to deploy the nginx image from the Docker Hub:

```
kubectl create deployment nginx-deployment --image=nginx

kubectl get pods

kubectl get deployment

kubectl expose deployment nginx-deployment --port=80 --type=LoadBalancer

kubectl get service
```
