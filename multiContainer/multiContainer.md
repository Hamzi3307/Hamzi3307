## Multi Container Pods

### Sharing Data:
We need to mount the volumes to both the containers if we want the containers to share the data.

### Designs
There are 3 common patterns, when it comes to designing multi-container PODs. 
1. side car pattern: The first and what we just saw with the logging service example. 
2. the adapter pattern.
3. the ambassador pattern.