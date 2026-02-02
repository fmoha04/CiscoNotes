> routing VLAN config (router-on-a-stick)
```
Router(config)# int g0/0/0
Router(config-if)# no shutdown
Router(config)# int g0/0/0.51
Router(config-subif)# encapsulation dot1q 51
Router(config-subif)# ip add 10.0.51.1 255.255.255.0
Router(config-subif)# ip nat inside
```

> show configs
```
Router# show running-config // muestra config actual almacenada en RAM
Router# show vlan brief // lista VLAN´s configuradas en el SW y sus puertos de acceso
Router# show interfaces trunk // lista los puertos con enlaces trunk y Vlans permitidas 
Router# show ip interface brief // muestra info acerca de las interfaces como las IP´s
```

> copy config(RAM) to NVRAM
```
Router# copy running-config startup-config
```

> set a hostname
```
Router(config)# hostname router1
```

