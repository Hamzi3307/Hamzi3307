## Metric Server
It is the main in memory metrics collector of the k8s cluster
I gathers the information regarding CPU and Memory Utilization fronm cAdvisor in kubelet.

## Installation

1. Minikube

    - minikube enable addons metrics-server

2. Other Clusters:

    - git clone github.com/metric-server-repository
    - cd metrice-server
    - kubectl apply -f .