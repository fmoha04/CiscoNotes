> [ 1 - CONFIGURACIÓN BÁSICA DEL ROUTER ]

```
.......................................
```

> [ 2 - CREACIÓN DE UN TRUNK ADICIONAL EN EL SWITCH 2 ]

````
Switch2(config)# interface FastEthernet 0/2
Switch2(config-if)# switchport mode trunk
Switch2(config-if)# no shutdown
````

> [ 3 - CREACIÓN DE UNA VLAN DE GESTIÓN PARA EL ROUTER ]

````
Router(config)# interface GigabitEthernet 0/0
Router(config-if)# no ip address
Router(config-if)# no shutdown
````
````
Router(config)# interface GigabitEthernet 0/0.99
Router(config-subif)# encapsulation dot1q 99
Router(config-subif)# ip address 10.0.99.254 255.255.255.0
````
````
PC --> 10.0.99.10/24 GW 10.0.99.254 --> ssh admin@10.0.99.254
````

> [ 4 - CREACIÓN DE LAS VLAN DE CLIENTES (100) Y DE SERVIDORES (200) EN EL ROUTER ]

````
Router(config)# interface GigabitEthernet 0/0.100
Router(config-subif)# encapsulation dot1q 100
Router(config-subif)# ip address 10.0.100.254 255.255.255.0
````
````
Router(config)# interface GigabitEthernet 0/0.200
Router(config-subif)# encapsulation dot1q 200
Router(config-subif)# ip address 10.0.200.254 255.255.255.0
````
````
show ip interface brief
````

> [ 5 - COMPROBACIÓN DE LA CONECTIVIDAD ENTRE LAS DISTINTAS REDES ]

````
ping 10.0.200.server
traceroute 10.0.200.server
````

> [ 6 - (OPCIONAL) ACCESO A INTERNET ]

````
Router(config)# interface range g0/0.99 , g0/0.100 , g0/0.200
Router(config-if-range)# ip nat inside
Router(config)# interface GigabitEthernet 0/1
Router(config-if)# ip address dhcp
Router(config-if)# ip nat outside
Router(config-if)# no shutdown
````
````
Router(config)# access-list 1 permit 10.0.0.0 0.0.255.255
````
````
Router(config)# ip nat inside source list 1 interface GigabitEthernet 0/1 overload
````
````
show ip nat translations
show ip nat statistics
````

