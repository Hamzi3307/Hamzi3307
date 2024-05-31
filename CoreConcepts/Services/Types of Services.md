## ClusterIP
 - Applications need to communicate internally to backend and DBs
 - CLusterIP service is used for this purpose
 - Default type is CLusterIP

## NodePort
 - Listens to a port on Node's IP from 30000-65000.
 - Application is automaticaly accessible via all Node's IPs on same port.
 - Uses Algorithm: Random
        SessionAffinity: Yes

## LoadBalancers
 - It works only in supported cloud platforms
 - If you set the type to LoadBalancer in a non supported environment, it will have the same    effect as NodePort.