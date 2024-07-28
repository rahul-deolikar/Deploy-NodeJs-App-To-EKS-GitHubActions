## Deploy-NodeJs-App-To-EKS-Using-Actions
#### launch one instance t2.medium


**1:Install eksctl CLI tool for creating EKS Clusters on AWS**
##### download eksctl CLI tool for creating EKS Clusters on AWS
```` 
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
````
##### move eksctl setup to /usr/local/bin directory

````
sudo mv /tmp/eksctl /usr/local/bin
```` 
##### To check eksctl version
```` 
eksctl version
````

**2:Install Kubectl on Ubuntu**
##### Add the kubectl GPG key
````
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
````
##### Create apt repo for kubectl
````
sudo touch /etc/apt/sources.list.d/kubernetes.list
````
##### Add Kubernetes official apt repo
````
echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
````
##### Update the system packages
````
sudo apt-get update
````
##### Install kubectl on Ubuntu using below command
````
sudo apt-get install -y kubectl
````

**3:Install AWS CLI on Ubuntu**
##### Download the aws cli bundle using below command
````
sudo apt install unzip -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
````


**4:Configure AWS CLI**
##### To connect AWS using CLI we have configure AWS user using below command
````
aws configure
````

**5:Create Amazon EKS cluster using eksctl**
````
eksctl create cluster --name demo-ekscluster --region us-east-1 --version 1.27 --nodegroup-name linux-nodes --node-type t2.micro --nodes 2
````

**6:Check nodes in EKS cluster**
To check the details about your node run the below command
````
kubectl get nodes
````
````
kubectl get namespace
````
````
kubectl describe nodes ip-192-168-14-229.us-east-1.compute.internal
````


**create ecr repository**
##### private>reponame>create

**Create github repository**
##### deploy nodejs app to eks using github action
##### now clone the repo and open folder in vscode
##### need to implement the same in aks cluster 
