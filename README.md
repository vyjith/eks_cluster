## How to create the eks cluster. Here is the easiest way to install the eks cluster...

Use the following link for creating the eksctl tool..

https://github.com/weaveworks/eksctl/blob/main/README.md#installation

https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html

In the above document will help you to install the eksctl but you need to install the kubectl on the worker node so you can use the following link for installing the kubectl in the machine. 

https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

I am using the version amd64 based hardware type so I am using the first link. Here I am shared the linux os distribution so select your appropriate version from the above url...

```
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.26.2/2023-03-17/bin/linux/amd64/kubectl
```

The following is the Checksum so download it....
```

curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.26.2/2023-03-17/bin/linux/amd64/kubectl.sha256
```

Use the following command for verifying the checksum value....
```
sha256sum -c kubectl.sha256
```

Finally, use the following command for creating the eks cluster. I have tried this and it was working fine. Check it and let me know you feedback....

The below configration, the name of the cluster will be vyjith-cluster, kubernetes version is 1.25, regieon is ap-south-1, nodegroup-name is linux-nodes, node-type is t2 micro and the node count it 2.. 

```

eksctl create cluster --name vyjith-cluster --version 1.25 --region ap-south-1 --nodegroup-name linux-nodes --node-type t2.micro --nodes 2
```

The above command will take atelease 30 minutes to complete the cluster....

Check the following command for the the node status.....
```
kubectl get nodes
```
```
kubectl get ns
```

For deleting the kubernetes cluster use the following command..
```
eskctl delete cluster --name test-cluster  -- for deleting the amzone cluster
```

# Fargate Cluster creation...

```
eksctl create cluster --name demo --region ap-south-1 --fargate
```

For deleting the fargate cluster --

```
eksctl delete cluster --name demo
```
