## Static Pod
Think of a scenario where we only have one worker node with kubelet installed.

Will we be able to deploy our pods on that node?

In the absence of a kube-api server how can we pass our pod.yaml to the kubelet

Here is where static pods comes into picture.

## Path on Worker Node:
this is the path where we can put the files for our static pods

    - cd /etc/kubernetes/manifests

1. In case a pod fails or we make any change to the pod.yaml the pod is restarted.
2. In case we delete the file from here, the pod is automatically deleted from the node.
3. Can be viewed y apiserver using get pod but cant be edited or deleted.
    
    - kubectl get pod
    - kubectl delete pod pod-name (doesnot work)
## Configure the above path:
1. Pass the path as a parameter to the kubelet.

    - ExecStart=/usr/local/bin/kubelet --pod-manifest-file=/etc/kubernetes/manifests
2. Pass a config.yaml file as a param to the kubelet

    - ExecStart=/usr/local/bin/kubelet --config=config.yaml
    - ./config.yaml > staticPodPath: /etc/kubernetes/manifests