## Steps required in Certificate Signing:
### Create a key and csr:
``` bash
    openssl
```

### Create a CSR Object using yaml file:
``` bash
    kubectl apply -f csr.yaml
```

### Review the Request:
``` bash
    kubectl get csr name -o yaml
```

### Approve or Deny the Request:
``` bash
    kubectl certificate approve/deny name
```

### Get Certificate:
``` bash
    kubectl get csr name -o yaml
```
