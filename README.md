# Setup deployment server 
 
- Need to open following ports in security group of the deployment server

       http ( 80 ) , https ( 443) , ssh (22)
====================================================================================
 
 - To install Docker use the following commands ....
  
     sudo yum install docker
  
     sudo systemctl enable docker (set to start service on boot)
  
      sudo systemctl start docker (start the service)
     
     
 Validate installation using command 'sudo systemctl status docker'

 ===================================================================================
 

 - To install Kubernetes , use the following commands..
 
 
 	curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.31.2/2024-11-15/bin/linux/amd64/kubectl
	chmod +x ./kubectl
        mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH
	   
  Validate installation using command kubectl . Output will be help recommendation from kubectl
  
======================================================================================


 - To install eksctl , use the following commands...

	export ARCH=amd64
	export PLATFORM=$(uname -s)_$ARCH
	curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"
	tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz
	sudo mv /tmp/eksctl /usr/local/bin

 Validate installation using command eksctl. Output will be help recommendation from eksctl

==========================================================================================

- To install git use the following commands ...
  
  
     sudo yum install git
     
  
 Validate installation using command git . Output will be help recommendation from git.

 
==========================================================================================

- To install Node.js use the following commands...
  

    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
    
    source ~/.bashrc
    
    nvm install --lts
    
  
Validate installation using command npm. Output will be a help recommendation from npm.

===========================================================================================

- To install Terraform use the following commands ...
  

   sudo yum install -y yum-utils
   
   sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo   // Add hadicorp repo
   
   sudo yum -y install terraform
   
   
Validate installation using command terraform -v . 

============================================================================================

- From the deployment server, run the following command to install Helm:
  
   curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
   
   chmod 700 get_helm.sh
   
   ./get_helm.sh
   
Validate installation using command helm . Output will be a help recommendation from helm.


===============================================================================================

- Containerize Application

   Two applications along with Dockerfile has been uploaded in following paths
  
  ./events-api
  
  ./events-website
  

================================================================================================
- Build Kubernetes Cluster
   K8s cluster created in fargate . Corrosponding yaml file stored in following location

    ./eks_cluster_config/cluster.yaml

================================================================================================
- Containerize Application
   Images placed in public docker hub

  https://hub.docker.com/repositories/amlandocker
================================================================================================
- Kubernetes Cluster creation

  k8s file kept in following folder ...
  
   ./eks_cluster_config

  version of k8s 1.31 ( must be over 1.3 )

=================================================================================================



  



  
  
  
  

  
   

