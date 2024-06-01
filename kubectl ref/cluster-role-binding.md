## Cluster Role Binding
    - 

Q: Create a cluster role binding for user1, user2, and group1 using the cluster-admin cluster role

Ans:

    - kubectl create clusterrolebinding cluster-admin-bind --cluster-role=cluster-admin --user=user1 --user=user2 --group=group1
