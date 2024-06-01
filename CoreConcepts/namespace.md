## Namespaces

# Create NS:
 - we can write namespace using def file as ns.yaml
 - kubectl create namespace ns-name

# Using NS:
 - kubectl create -f pod.yaml --namespace=ns-name
 - we can write it in pod def file in metadata.
    metadata:
    name: nginx-pod
    labels: 
        app: web-server
        tier: frontend
    namespace: ns-name

# Access a resource in a NS:
 - In the same ns, a pod can access a resource by its name only.
   e.g: db_host("db-service")
 - In a diferent namespace, a pod cannot access by just its name
   e.g: db_host("db-service")
 - It will be accessed by this way rather.
   e.g: db_host("db-service.ns-name.svc.cluster.local")

# Switch Namespace:
 - to switch the default namespace to another one use
   kubectl config set-context $(kubectl config current-context) --namespace=dev

# Resources for a Namespace:
 - To limit resources for a namespace 
    > Create a Resource Quota i.e: quota.yaml
    > Specify the namespace in the metadata of that file