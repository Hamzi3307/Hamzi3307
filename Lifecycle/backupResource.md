## Resources Backup:
If we create our cluster resources using the declarative way, we can manage the files in a GitHub or any other VCS. 
And then we can restore our cluster by just running the kubectl apply command as:

    git clone github.com/username/repo.git
    cd repo
    kubectl apply -f ./

In case we have created our cluster using imperative way, we can still get the confiuration files using command:

    kubectl get all --all-namespaces -o yaml > all-deploy-svc.yaml
    # to restore the cluster
    kubectl apply -f all-deploy-svc.yaml


> NOTE: Mention the following params with the etcdctl command utility
``` bash
    ETCDCTL_API=3 etcd \
    snapshot save snapshot.db \
    --endpoints=https://127.0.0.1:2379
    --cacert=/path/etc/etcd/ca.crt
    --cert=/path/etc/etcd/etcd-server.crt
    --key=/path/etc/etcd/etcd-server.key
```

## ETCD Backup:
ETCD is the main component where all the details of the cluster are stored.
While creating an etcd server we pass a parameter where our whole data is stored.

    --data-dir /var/lib/data

### Backup using etcdctl:
etcdctl come with a snapshot command to deal with backups and restorations.
To take a backup using etcdctl will run the command as;

```bash
   ETCDCTL_API=3 etcdctl \
   snapshot save path/to/snapshot.db
```
### Backup Status:
```bash
   ETCDCTL_API=3 etcdctl \
   snapshot status path/to/snapshot.db
```
# Restore DB using snapshot:
There are following steps to restore the database using snapshot utility

1. Stop the kube-apiserver:
```bash
   service stop kube-apiserver
```
2. Restore the etcd to a new --data-dir:
```bash
   ETCDCTL_API=3 etcdctl \
   snapshot restore path/to/snapshot.db
   --data-dir /var/lib/backup-data
```
3. Edit the --data-dir in the etcd-server file:
```bash
   Execstart=/usr/local/bin/etcd
   ---
   --data-dir /var/lib/backup-data
```
4. Restart the etcd server:
``` bash
    systemctl daemon-reload
    service etcd restart 
```
5. Start the API-server:
``` bash
    service start kube-apiserver
```