## CronJob
It is exactly the same as a single entry in crontab (cron table)

## Flags

1. image:
2. schedule:

## Examples:
> Create a cron job
    - kubectl create cronjob my-job --image busybox:1.29 --schedule "* * * * *"

> Create a cronJob with command
    - kubectl create cronjob my-job --image busybox:1.28 --schedule "* * * * *" -- date

## Manifest File
> Present in same directory with name cronjob.yaml