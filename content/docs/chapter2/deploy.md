---
title: Deploy
linktitle: Deploy
toc: true
type: book
weight: 4
---

## Azure Kubernetes Service
If build, test, and deploy is successful, the service is deployed to Azure Kubernetes Cluster. This is how the cluster works - 
![img](/i7.png)

Kubernetes architecture involves a cluster of nodes. **Nodes** are the smallest unit of computer hardware in Kubernetes. Nodes store and process data. Nodes can be physical computers or virtual machines (VMs). Nodes are two types - Master nodes or control planes and worker nodes. Inside worker nodes run multiple **pods**, which are the smallest execution unit in Kubernetes. A pod encapsulates one or more containerized applications (such as Docker containers). Every cluster has at least one worker node. The job of the **worker node(s)** is to host the Pods that are the components of the application workload. **The master nodes** manage the worker nodes and the Pods in the cluster. The processes running inside worker nodes are called worker processes, and those running in master nodes are called master processes. In production environments, the control plane usually runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolerance and high availability. For this process, the worker and master processes are running in the same node. 

As seen in the figure above, the master processes include API server, controller manager, scheduler, and etcd. 
1. **API server** - The API server is a component of the Kubernetes control plane that exposes the Kubernetes API. It is the entry point to the Kubernetes cluster. The cluster can be controlled by the developers by using Kubectl, a command line tool that connects to the API server to send commands. 
2. **Etcd** - Consistent and highly-available key value store used as Kubernetes' backing store for all cluster data. 
3. **Scheduler** - Control plane component that watches for newly created Pods with no assigned node, and selects a node for them to run on. 4. **Controller manager** - Control plane component that runs controller processes. Its responsibilities include noticing and responding when nodes go down, joining services and pods, etc. 

The worker process includes two **deployments**, frontend and backend. Each deployment contains two pods running the same thing. The pods are replicas of each other. So, the frontend deployment contains two replicas running the React frontend in a docker container; and the backend contains two replicas running the Node API in a docker container. The pods can communicate with each other with the help of **services**. These services are strictly internal and not accessible from the outside. Requests from the client reach **Ingress**, which exposes the service to the clients and the outside world. Ingress maps ports of the cluster to an externally accessible port. In this case, Ingress exposes both the backend service and frontend service to the outside world. Clients' requests can now reach the frontend service, which sends the request to one of the two pods in the **frontend deployment**. Similarly, the frontend, now in the clients’ machine, can access the backend service from the NodePort. Again, the backend service acts as a load balancer for the two pods in deployment. In order to function, the backend pods require nonsensitive configuration data like database URL and sensitive data like API keys. These information are fetched from **config map and secrets** storage respectively. 

It is to be noted that the services come with a built in **load balancer**. Which means the system will handle itself when one replica goes down. In case of rising workload, **the number of replicas can be increased by changing one line of code**, and the rest is handled by kubernetes. 
