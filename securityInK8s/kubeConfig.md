# Kube Config:

### Overview
A kubeconfig file is used by Kubernetes to configure access to clusters. It contains information about clusters, users, and contexts to connect to the clusters. The kubeconfig file is essential for the kubectl command-line tool to function correctly.

### Structure:
A typical kubeconfig file is structured in YAML format and consists of several key sections:

- clusters: Defines the clusters you can connect to.

- users: Defines the users or service accounts that can access the clusters.

- contexts: Defines the contexts that combine a cluster, a user, and a namespace.

- current-context: Specifies the default context to use.

### Clusters Section
The clusters section contains a list of clusters, each defined by:

- name: A unique identifier for the cluster.
- cluster: A map that includes:
    - certificate-authority-data: The base64-encoded certificate authority data for the cluster.
    - certificate-authority: path to ca.crt
    - server: The API server endpoint.

### Users Section
The users section contains a list of users, each defined by:

- name: A unique identifier for the user.

- user: A map that includes:

    - client-certificate-data: The base64-encoded client certificate data.

    - client-key-data: The base64-encoded client key data.

### Contexts Section
The contexts section contains a list of contexts, each defined by:

- name: A unique identifier for the context.

- context: A map that includes:

    - cluster: The name of the cluster to use.

    - user: The name of the user to use.

    - namespace: The namespace to use.

### Using Kubeconfig
To use a specific kubeconfig file, set the KUBECONFIG environment variable:
``` bash
    export KUBECONFIG=/path/to/your/kubeconfig
```

Alternatively, you can specify the --kubeconfig flag with the kubectl command:
``` bash
    kubectl --kubeconfig=/path/to/your/kubeconfig get pods
```

### Basic Commands:

    kubectl config --help
    kubectl config use-context my-context
    kubectl config show-context my-context
