> create an vlan on interface and name it
```
Switch(config)# vlan 51
Switch(config)# name Servers
```

> other commands
```
Switch(config)# vlan 51 name Servers // create vlan and name it on one command
Switch(config)# vlan 10,20,30 // create various vlans on one command
Switch(config)# no vlan 10 // delete a specific vlan
Switch# delete flash:vlan.dat // delete vlan info
```

> assign an vlan to an interface in mode access
```
Switch(config)# int fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 51
Switch(config-if)# no shutdown
```

> disable mode access port, changes to vlan1
```
Switch(config-if)# no switchport access vlan
```

> assign an vlan to an interface in mode trunk
```
Switch(config)# int gig0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 51,52,99
Switch(config-if)# switchport trunk native vlan 1000
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
Switch# show running-config // muestra config actual almacenada en RAM
Switch# show vlan brief // lista VLAN´s configuradas en el SW y sus puertos de acceso
Switch# show interfaces trunk // lista los puertos con enlaces trunk y Vlans permitidas 
Switch# show ip interface brief // muestra info acerca de las interfaces como las IP´s
```

