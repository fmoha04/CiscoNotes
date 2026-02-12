> Set ACL´s
```
Router(config)# access-list 1 permit 10.0.100.0 0.0.0.255
Router(config)# access-list 2 permit 10.0.200.0 0.0.0.255
```

> Assign NAT roles
```
Router(config)# interface GigabitEthernet 0/0.200
Router(config-subif)# ip nat inside
Router(config-subif)# exit
Router(config)# interface GigabitEthernet 0/1
Router(config-if)# ip nat outside
```

> Configure NAT (PAT)
```
Router(config)# ip nat inside source list 1 interface GigabitEthernet 0/1 overload
Router(config)# ip nat inside source list 2 interface GigabitEthernet 0/1 overload
```

> Configure SNAT
```
access-list 1 permit 10.0.0.0 0.0.0.255
ip nat inside source list 1 interface GigabitEthernet 0/1 overload
interface GigabitEthernet 0/0
ip nat inside
interface GigabitEthernet 0/1
ip nat outside
ip route 0.0.0.0 0.0.0.0 192.168.133.254
```

> Adding an Static Route
```
Router(config)# ip route 0.0.0.0 0.0.0.0 192.168.133.254
```

> Show configs
```
Router# show ip nat translations
Router# show ip nat statistics
Router# show ip route
```

