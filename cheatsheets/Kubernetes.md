# Kubernetes
Open Source system for automaticly deployment, scaling and management of containerized applications

## Bestandteile:
* Node - machine where k8s ist installed, worker machine where container will be launched managed by k8s, 
* auf jedem Node sind installiert:
  * kubelet: das mit dem Kubernetes Master kommuniziert.
  * kube-proxy, ein Netzwerk-Proxy, der die Netzwerkdienste von Kubernetes auf jedem Node darstellt.
* Cluster - set of nodes
* Master - k8s node, orchestrator
  * API Server
  * etcd
  * Scheduler
  * Controller

## Kubernetes Basisobjekte
* Pod:  smallest deployable units of computing that you can create and manage in Kubernetes.
* Service:  is a method for exposing a network application that is running as one or more Pods in your cluster.
* Volume
* Namespace: a mechanism for isolating groups of resources within a single cluster
* Controller (Highlevel Abstraktionen on top der Basisobjekte)
  * ReplicaSet
  * Deployment
  * StatefulSet
  * DaemonSet
  * Job