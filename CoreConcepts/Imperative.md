## Definition:
    Various Resources in K8s can be created using commands directly without any files as give below.

## Pod
    - kubectl run pod_name --image image_name --labels key:value,key:value

## Service
    We have two imperative ways of creating services
    a) kubectl expose pod pod_name --name svc_name --port target_port --type svc_type
    b) kubectl create service svc_name --type svc_type --tcp=80:80 --node-port=30080
    In Option a: 
        - unable to specify nodeport
        - detect the selector portion from the mentioned pod_name 
    In Option b:
        - we can specify nodeport
        - cannot detect the selectore portion

## Deployment & ReplicaSet:
    - kubectl create deployment nginx --image=nginx --replicas=2

    You can also scale a deployment using the kubectl scale command.
    - kubectl scale deployment nginx --replicas=4 

## Namespace
    - kubectl create namespace ns_name