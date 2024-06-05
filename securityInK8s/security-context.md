# Linux Capabilities:

Linux Capabilities are 

## Docker Security:
Docker utilizes linux capabilities as it does not gives all permissions to the root user of the container as given in image.
### Docker Default Privilages:

```bash 
    docker run -p 80:80 image_name  
```
![alt text](docker-default.png)

### Docker Add Privilages:
```bash 
    docker run -p 80:80 --cap-add MAC_ADMIN image_name  
```
![alt text](cap-add.png)

### Docker Drop Privilages:
```bash 
    docker run -p 80:80 --cap-drop KILL image_name  
```
![alt text](cap-drop.png)

### Docker Full Privilages:
```bash 
    docker run -p 80:80 --priviliged image_name  
```
![alt text](full-cap.png)

# Security Context in K8s:

### Manage Capabilities:
To manage linux capabilities and user running the pod or container we do these configuration

![alt text](security-k8s.png)

### RunAsUser:
This is an alternative of this command:
```bash
    docker run -p 80:80 --user 1000 image_name
```