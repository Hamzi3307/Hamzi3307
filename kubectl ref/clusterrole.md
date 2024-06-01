## Cluster Role
    - 

Q1: Create a cluster role named "pod-reader" that allows user to perform "get", "watch" and "list" on pods?
Ans:
    - kubectl create clusterrole pod-reader --verb=get,watch,list --resource=pods

Q2: Create a cluster role named "pod-reader" with ResourceName specified
Ans:   
    - kubectl create clusterrole pod-reader --verb=get,watch,list --resource=pods --resource-name=pod_name --resource-name=pod_name2

Q3: Create a cluster role named "foo" with API Group specified
Ans:
    - kubectl create clusterrole foo --verb=list,of,verb --resource=rs.extensions

Q4: Create a cluster role named "foo" with SubResource specified
Ans:
    - kubectl create clusterrole foo --verb=list,of,verb --resource=pods,pods/status

Q5: Create a cluster role name "foo" with NonResourceURL specified
Ans:
    - kubectl create clusterrole foo --verb=list,of,verb --non-resource-url=/logs/*

Q6: Create a cluster role name "monitoring" with AggregationRule specified
Ans:
    - kubectl create clusterrole monitoring--aggregation-rule="rbac.example.com/aggregate-with-monitoring=true"
