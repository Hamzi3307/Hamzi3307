## Labels and Selectors

> How many PODs are in the finance business unit (bu)?

    - kubectl get pod --selector bu=finance

> How many objects are in the prod environment including PODs, ReplicaSets and any other objects?

    - kubectl get all --selector env=prod

> Identify the POD which is part of the prod environment, the finance BU and of frontend tier?

    - kubectl get pod --selector env=prod,bu=finance,tier=frontend