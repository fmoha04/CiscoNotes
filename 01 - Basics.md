> Set a IP address
```
Switch(config)# interface fa0/1
Switch(config-if)# ip address 192.168.10.1 255.255.255.0
Switch(config-if)# no shutdown
```

> Set a static route
```
Router(config)# ip route <dest.network> <dest.mask.network> <next.hop>
```

> Clock Set
```
Switch# show clock
Switch# clock set hh:mm:ss dd yyyy
```

> Set a Hostname
```
Switch(config)# hostname <new-hostname>
```

> Disable DNS resolution
```
Switch(config)# no ip domain-lookup
```

> Set a identity-domain
```
Switch(config)# ip domain-name <domain.name>
```

> Set a password for console access
```
Switch(config)# line con 0
Switch(config-line)# password <password>
Switch(config-line)# login
```

> Set a password for privileged access
```
Switch(config)# enable secret <password>
```

> Encrypt Passwords
```
Switch(config)# service password-encryption
```

> Configure ssh key encryption method
```
Switch(config)# crypto key generate rsa modulus 1024

```

> Set a SSH version
```
Switch(config)# ip ssh version <version>
```

> Set a user+pass for SSH access
```
Switch(config)# username <username> secret <password>
```

> Configure SSH access { login local: user+pass }
```
Switch(config)# line vty 0 4
Switch(config-line)# transport input ssh
Switch(config-line)# login local
```

> Configure SSH access { login local: pass }
```
Switch(config)# line vty 0 4
Switch(config-line)# transport input ssh
Switch(config-line)# login
```

> Set a login banner
```
Switch(config)# banner motd # <message> #
```

> Show running configurations
```
Switch# show running config
Switch# show ip interface brief
Router# show ip route
```

