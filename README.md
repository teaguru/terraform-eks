# Learn Terraform - Provision an EKS Cluster

This repo is a companion repo to the [Provision an EKS Cluster learn guide](https://learn.hashicorp.com/terraform/kubernetes/provision-eks-cluster), containing
Terraform configuration files to provision an EKS cluster on AWS.

# Learn Terraform - Provision an EKS Cluster

This repo is a companion repo to the [Provision an EKS Cluster learn guide](https://learn.hashicorp.com/terraform/kubernetes/provision-eks-cluster), containing
Terraform configuration files to provision an EKS cluster on AWS.

# ~/.kube/config
aws eks --region $(terraform output -raw region) update-kubeconfig --name $(terraform output -raw cluster_name)
cat  /Users/hero/.kube/config
aws eks get-token --cluster-name education-eks-3VI0zzrj
kubectl create namespace prod
helm install gitlab-runner  gitlab/gitlab-runner -n prod -f ./val.yaml

kubectl create serviceaccount gitlab
And assign it the cluster-admin role using:
kubectl create clusterrolebinding gitlab-cluster-admin --clusterrole=cluster-admin --serviceaccount=default:gitlab
learn-terraform-provision-eks-cluster hero$ KUBE_EDITOR="nano" kubectl edit -n kube-system deployment metrics-server
deployment.apps/metrics-server edited

ADMIN_USER_TOKEN_NAME=$(kubectl -n kube-system get secret | grep admin-user-token | cut -d' ' -f1)
$ echo $ADMIN_USER_TOKEN_NAME

admin-user-token-k4s7r
# The suffix is auto-generated

$ ADMIN_USER_TOKEN_VALUE=$(kubectl -n kube-system get secret "$ADMIN_USER_TOKEN_NAME" -o jsonpath='{.data.token}' | base64 --decode)
$ echo "$ADMIN_USER_TOKEN_VALUE"