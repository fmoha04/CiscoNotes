> create an vlan on interface and name it
```
Switch(config)# vlan 51
Switch(config)# name servers
```

> assign an vlan to an interface in mode access
```
Switch(config)# int fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 51
Switch(config-if)# no shutdown
```

> assign an vlan to an interface in mode trunk
```
Switch(config)# int gig0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 51,52,99
Switch(config-if)# no shutdown
```

> add SW manage vlan IP
```
Switch(config)# int vlan 99
Switch(config-if)# ip add 10.0.99.201 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
Switch(config)# ip default-gateway 10.0.99.1
```

> show configs
```
show running-config
show vlan brief
show interfaces trunk
```
> copy config(RAM) to NVRAM
```
copy running-config startup-config
```



