# Guided-Projects-Coursera-Kubernetes

## [1. Container Orchestration using Kubernetes](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Container%20Orchestration%20using%20Kubernetes)

Learning Objectives
- Understand and create various Kubernetes objects like pods, replication controller, deployment and services.
- Understand rolling updates and rollbacks in Kubernetes

The hands-on project on Container Orchestration using Kubernetes is divided into the following tasks:

## Task 1: Create and deploy your first pod in your Kubernetes cluster
### Execute Commands on Terminal:
    mkdir yml  
    cd yml  
    vi nginx_pod.yml
   
Enter into Insert mode with Press Esc+I

  
### Inside nginx_pod.yml
    apiVersion: v1    
    kind: Pod    
    metadata:     
            name: my-nginx-pod            
    spec:    
            containers:            
                      - name: my-nginx                      
                        image: nginx

Save the file with ESC and :wq!

### Execute Commands on Terminal
    sudo minikube start --vm-driver=none  ---> kubectl configured to use minikube
    
    sudo kubectl apply -f nginx_pod.yml ---> pod/my-nginx-pod created
    
    sudo kubectl get pods --->  display running pods

## Task 2: Create and deploy replication controller in your cluster to maintain the state of your pods
### Execute Commands on Terminal

    clear
    vi nginx_rc.yml

Enter into Insert mode with Press Esc+I

### Inside nginx_rc.yml

    apiVersion: v1
    kind: ReplicationController
    metadata:  
            name: my-nginx-rc
    spec: 
            replicas: 10
            selector: 
                    app: nginx
            template: 
                    metadata: 
                            name: my-nginx-pod
                            labels: 
                                  app: nginx
                    spec:
                            containers:
                                      - name: nginx
                                        image: nginx
                                    
Save the file with ESC and :wq!

### Execute Commands on Terminal
    sudo kubectl apply -f nginx_rc.yml  ---> replicationcontroller/my-nginx-rc created


- Task 3: Enable access to an application running in your pod through NodePort service
- Task 4: Create your first deployment in Kubernetes cluster
- Task 5: Perform rolling updates and rollbacks in Kubernetes

## [2. Monitoring Kubernetes Cluster using Prometheus and Grafana](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Monitoring%20Kubernetes%20Cluster%20using%20Prometheus%20and%20Grafana)

## [3. Containerised app development with Azure Kubernetes Service](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Containerised%20app%20development%20with%20Azure%20Kubernetes%20Service)

## [4. Kubernetes in AWS: Create Cluster in EKS in your own VPC](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Kubernetes%20in%20AWS:%20Create%20Cluster%20in%20EKS%20in%20your%20own%20VPC)

## [5. Kubernetes: Create Multi-App Cluster with Ingress & Logging](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Kubernetes:%20Create%20Multi-App%20Cluster%20with%20Ingress%20&%20Logging)

## [6. Deploy an App in AWS Elastic Kubernetes Cluster using EKSCTL](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Deploy%20an%20App%20in%20AWS%20Elastic%20Kubernetes%20Cluster%20using%20EKSCTL)

## [7. Deploy a Web Application in Azure Kubernetes Service](https://github.com/gjkaur/Guided-Projects-Coursera-Kubernetes/tree/main/Deploy%20a%20Web%20Application%20in%20Azure%20Kubernetes%20Service)
