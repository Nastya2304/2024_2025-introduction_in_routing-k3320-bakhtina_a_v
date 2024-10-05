## R01

```
[admin@RO1] > export
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan10 vlan-id=10
add interface=ether3 name=vlan20 vlan-id=20
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip pool
add name=pool10 ranges=192.168.10.10-192.168.10.253
add name=pool20 ranges=192.168.20.10-192.168.20.253
/ip dhcp-server
add address-pool=pool10 disabled=no interface=vlan10 name=server10
add address-pool=pool20 disabled=no interface=vlan20 name=server20
add address=192.168.20.1/24 interface=vlan20 network=192.168.20.0
/ip dhcp-client
add disabled=no interface=ether1
/ip dhcp-server network
add address=192.168.10.0/24 gateway=192.168.10.1
add address=192.168.20.0/24 gateway=192.168.20.1
/system identity
set name=RO1
```

## SW01.01

```
/interface bridge
add name=bridge_10
add name=bridge_20
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan10 vlan-id=10
add interface=ether4 name=vlan10_1 vlan-id=10
add interface=ether3 name=vlan20 vlan-id=20
add interface=ether5 name=vlan20_1 vlan-id=20
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/interface bridge port
add bridge=bridge_20 interface=vlan20
add bridge=bridge_20 interface=vlan20_1
add bridge=bridge_10 interface=vlan10
add bridge=bridge_10 interface=vlan10_1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=bridge_10
add disabled=no interface=bridge_20
/system identity
set name=SW01.01
```

## SW02.01

```
[admin@SW02.01] > export
/interface bridge
add name=bridge_10
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan10 vlan-id=10
add interface=ether4 name=vlan10_1 vlan-id=10
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/interface bridge port
add bridge=bridge_10 interface=vlan10
add bridge=bridge_10 interface=vlan10_1                           
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=bridge_10
/system identity
set name=SW02.01
```

## SW02.02

```
[admin@SW02.02] > export
/interface bridge
add name=bridge_20
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan20 vlan-id=20
add interface=ether4 name=vlan20_1 vlan-id=20
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/interface bridge port
add bridge=bridge_20 interface=*8
add bridge=bridge_20 interface=vlan20
add bridge=bridge_20 interface=vlan20_1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=bridge_20
/system identity
set name=SW02.02
```
