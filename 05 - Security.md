> MITIGATION MAC FLOODING WITH PORT-SECURITY
```
interface g1/0/3 // acceder a la interfaz deseada
switchport mode access // activar mode access
switchport port-security // activar port security
switchport port-security violation <mode> // establecer un port-security-mode
switchport port-security maximum <X> // poner un límite de mac´s
switchport port-security mac-address sticky // adherir primera mac
switchport port-security mac-address dirección <MAC> // fijar mac estatica
```

> MITIGATION AGAINST DHCP SPOOFING WITH DHCP SNOOPING
```
ip dhcp snooping
ip dhcp snooping vlan 1
interface FastEthernet0/2
ip dhcp snooping trust
```

> MITIGATION AGAINST ARP POISONING WITH DAI
```
ip dhcp snooping
ip dhcp snooping vlan 1
ip arp inspection vlan 1
int fa0/24
ip dhcp snooping trust
ip arp snooping trust
arp access-list servidor
permite ip host <IP> mac host <MAC>
ip arp inspection filter servidores vlan 1
ip arp inspection validate <src-mac> <dst-mac> <IP>
```

> MITIGATION AGAINST STP ATTACK WITH PORTFAST AND BPDUGUARD
```
int fa0/1
switchport mode access
spanning-tree portfast
exit
spanning-tree portfast default
exit
int fa0/1
spanning-tree bpduguard enable
exit
spanning-tree portfast bpduguard default
end
```

> INFO COMMANDS
```
clear mac address-table dynamic
show port-security interface fa3
show mac address-table
show mac address-table count
show ip dhcp snooping statistics
show ip dhcp snooping binding
show logging
no logging console
show ip arp inspection
show ip arp inspection interfaces
show spanning-tree summary
```

