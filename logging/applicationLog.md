## Application Logs

1. In case of a single container pods 

    - kubectl logs -f pod_name

2. In case of a Multi container pods 

    - kubectl logs -f pod_name container_name

## -f Flag:
It works to view logs in realtime coming like tail -f in simple linux.