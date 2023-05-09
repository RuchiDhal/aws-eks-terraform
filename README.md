# EKS (Amazon Elastic Kubernetes Service)

Deploying Kubernetes cluster in AWS-EKS using Terraform for Infrastructure as Code (IaC)

Below project demonstrates building an EKS cluster with the help of AWS provider and Kubernetes provider using Terraform. 

> **Note**
>
> You will need the following environment variables to be set in prior
>
> - `AWS_ACCESS_KEY_ID`
> - `AWS_SECRET_ACCESS_KEY`
> - `AWS_REGION`

## Create EKS cluster
In order to name your cluster you can choose a name or you can use terraform config file to create any random name

```
terraform init
terraform plan 
terraform apply
export CLUSTERNAME=$(terraform output -raw cluster_name)
```

Switch to eks-cluster directory and create the EKS cluster infrastructure.

```
cd eks-cluster
terraform init
terraform apply -var=cluster_name=$CLUSTERNAME

```


## Create Kubernetes resources
Now go to kubernetes-config directory to apply Kubernetes resources to the newly created cluster.


```
cd kubernetes-config
terraform init
terraform apply -var=cluster_name=$CLUSTERNAME
```




