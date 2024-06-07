# Networking Basics:

## Switch:
If we want two devices on same network communicate each other, we need the following steps:
1. We need to create Network Interface on each of those devices.

        // Command to show the network interfaces
         ip link 
2. Attach IPs to the interface i.e eth0, using command:
    ip addr add 192.168.1.10/24 dev eth0

## Router:
If we want to communicate with a device on another network,
1. Attach a router to the network.
2. Route has IPs on both the networks.
3. Now how to find another network ip on my network, This is where gateway comes into picture.

## Gateway:
We should tell each of our network devices that if you receive an IP from a specifc cidr route via the router.
1. To check the already configured routes in a system run the command.

    - route
2. Add a route to route from network A: 192.168.1.0/24 to B: 192.168.2.0/24 via 192.168.1.1/24 (router)

    - ip route add 192.168.2.0/24 via 192.168.1.1
3. Add a route to route from network B: 192.168.2.0/24 to A: 192.168.1.0/24 via 192.168.2.1/24 (router)

    - ip route add 192.168.1.0/24 via 192.168.2.1
4. We can add multiple routes via same gateway like:

    - ip route add 192.168.1.0/24 via 192.168.2.1
    - ip route add 192.168.3.0/24 via 192.168.2.1
    - ip route add 0.0.0.0 via 192.168.2.1 // default internet
