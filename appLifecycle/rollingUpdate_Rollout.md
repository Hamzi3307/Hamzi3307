## Rolling Update:
Deployment Strategies for update:
1. RollingUpdate: updates the Pods one by one
2. Recreate: Takes down the old replicaset and after that creates a new one.

### Command:

    - kubectl apply -f deploy.yaml

## Rollout:
Strategies are followed as given the above.
we do one revision back to the previous repicaset

### Command:

    - kubectl rollout undo deployment/deploy-name