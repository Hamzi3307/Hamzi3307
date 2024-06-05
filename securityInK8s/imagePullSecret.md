# ImagePullSecret

For kubernetes to authenticate with our private repository we use Secrets of type docker-registory
```bash
    kubectl create secret docker-registry regstry-cred \
    --docker-username=user
    --docker-password=password \
    --docker-server=server \
    --docker-email=email
```

Now use this secret in pod specification yaml file.

```bash
    ...
    imagePullSecrets:
    - name: regstry-cred
    ...
```