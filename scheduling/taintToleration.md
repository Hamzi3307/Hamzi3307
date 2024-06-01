## Taints and Tolerations
To check if there is a taint on my node named node01

    - kubectl describe node node01 | grep "Taint"

Create a taint on node01 with key of spray, value of mortein and effect of NoSchedule

    - kubectl taint node node01 spray=mortein:NoSchedule

## NodeSelectors:
To check if there is a label on my node named node01

    - kubectl describe node node01 | grep "label"

Create a label on node01 with key of spray, value of mortein 

    - kubectl label node node01 spray=mortein

use .spec.nodeSelector: spray=mortein

> NoteSelector is good but not enough we will have further control using nodeAffinity.