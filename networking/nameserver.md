# NameServer (DNS):

## /etc/hosts:
- If we want to give a name to a specific IP for a special system only.
    - echo "127.0.0.1   localhost" > /etc/hosts
    - echo "192.168.1.101   db" > /etc/hosts
    - echo "192.168.1.102   web" > /etc/hosts

## Nameserver:
- In case we have lots of servers and we want to use some names for those servers
- configuring the /etc/hosts on each server is a tedious work
- what if we configure the whole name and ips in a separate server and use that server.
- That server is now called NameServer.

        192.168.1.110       web.company.com
        192.168.1.111       front.company.com
        192.168.1.112       back.company.com
        192.168.1.113       db.company.com
        192.168.1.114       redis.company.com
        192.168.1.115       admin.company.com
        192.168.1.116       cron.company.com
        192.168.1.117       ftp.company.com
        192.168.1.118       test.company.com

## /etc/resolve.conf:
- how to use nameserver from  server here is the file where we need to make changes

        echo "nameserver        serverIP" >> /etc/resolve.conf
        // For accessing internet like facebook.com we use nameserver of google
        echo "nameserver        8.8.8.8" >> /etc/resolve.conf

## search:
- Now if we want to ping or access our comoany domains just by there subdomain
- Here search comes into picture.

        echo "search        company.com" >> /etc/resolve.conf
        // Now if we ssh or ping by subdomain it will still access that domain
        ping web
        - pinging web.company.com