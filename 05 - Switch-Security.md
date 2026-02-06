> MITIGATION AGAINST MAC FLOODING
```
interface g1/0/3
switchport mode access
switchport port-security
switchport port-security violation shutdown
```
> MITIGATION AGAINST DHCP SPOOFING
```
ip dhcp snooping
ip dhcp snooping vlan 1
interface FastEthernet0/2
ip dhcp snooping trust
```
> MITIGATION AGAINST ARP POISONING
```
ip arp inspection trust
/or/
arp access-list srvdhcp permit ip host 10.0.0.102 mac host xx:xx:xx:xx:xx:xx
ip arp inspection filter srvdhcp vlan 1
/or/
ip source binding xx:xx:xx:xx:xx:xx vlan n 10.0.0.102 interface 2
```

> OTHER COMMANDS
```
clear mac address-table dynamic
show port-security interface g1/0/3
show mac address-table
show mac address-table count
show ip dhcp snooping statistics
show ip dhcp snooping binding
show logging
no logging console
show ip arp inspection
show ip arp inspection interfaces
```

