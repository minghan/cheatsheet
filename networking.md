# Networking Stuff

Release dhcp:

    sudo dhclient -r

Obtain a fresh ip

    sudo dhclient

List arp

    arp -a

Refresh arp for a particular ip address

    ping 192.168.2.10

Delete arp entry

    arp -d 192.168.2.10

Add ip and corresponding mac

    arp -s 192.168.2.10 08:23:27:bb:2c:1e

Ping IPv6 address

    ping6 -c 1 -I eth0 fe80::21b:63ff:feab:e6a6
    

Bring up/down a network interface

    ifconfig eth1 up
    ifconfig eth1 down

Displays network connections, routing tables

    netstat -rn
    sudo netstat -plten | grep java

List open files

    lsof -i :22

[Ubuntu Networking Page](https://help.ubuntu.com/community/NetworkConfigurationCommandLine/Automatic)

Dump socket stats

    ss
