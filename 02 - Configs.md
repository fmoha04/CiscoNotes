> Copy config(RAM) to NVRAM
```
copy running-config startup-config
```

> Copy running config into flash
```
copy running-config flash:nombre_archivo
```

> Rename flash configs
```
rename flash:config.text flash:config.old
```

> Apply an existing flash config
```
copy flash:nombre_archivo running-config
```

> Delete VLAN config
```
write erase
delete flash:vlan.dat
reload
```

