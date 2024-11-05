## R01.NY

```
[admin@R01.NY] > export
/interface bridge
add name=bridge
add name=bridge_vpn
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:BD:27:52:DB:8E name=EoMPLS remote-peer=35.10.0.5 vpls-id=100:100
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.2
/interface bridge port
add bridge=bridge_vpn interface=ether5
add bridge=bridge_vpn interface=EoMPLS
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.2 interface=bridge network=35.10.0.2
add address=192.168.2.101/30 interface=ether3 network=192.168.2.100
add address=192.168.9.102/30 interface=ether4 network=192.168.9.100
add address=10.10.50.1/29 interface=bridge_vpn network=10.10.50.0
add address=192.168.10.101/30 interface=ether3 network=192.168.10.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.2 transport-address=35.10.0.2
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=35.10.0.2/32
add area=backbone network=192.168.9.100/30
add area=backbone network=192.168.2.100/30
/system identity
set name=R01.NY
```

## R01.LND

```
[admin@R01.LND] > export
/interface bridge
add name=bridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.3 interface=bridge network=35.10.0.3
add address=192.168.2.102/30 interface=ether4 network=192.168.2.100
add address=192.168.3.101/30 interface=ether3 network=192.168.3.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.3 transport-address=35.10.0.3
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone network=35.10.0.3/32
add area=backbone network=192.168.2.100/30
add area=backbone network=192.168.3.100/30
/system identity
set name=R01.LND
```

## R01.HKI

```
[admin@R01.HKI] > export
/interface bridge
add name=bridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.4
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.4 interface=bridge network=35.10.0.4
add address=192.168.3.102/30 interface=ether4 network=192.168.3.100
add address=192.168.8.102/30 interface=ether5 network=192.168.8.100
add address=192.168.4.101/30 interface=ether3 network=192.168.4.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.4 transport-address=35.10.0.4
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=35.10.0.4/32
add area=backbone network=192.168.3.100/30
add area=backbone network=192.168.4.100/30
add area=backbone network=192.168.8.100/30
/system identity
set name=R01.HKI
```

## R01.SPB:

```
[admin@R01.SPB] > export
/interface bridge
add name=bridge
add name=bridge_vpn
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:96:AE:D1:9C:3F name=EoMPLS remote-peer=35.10.0.2 vpls-id=100:100
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.5
/interface bridge port
add bridge=bridge_vpn interface=ether5
add bridge=bridge_vpn interface=EoMPLS
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.5 interface=bridge network=35.10.0.5
add address=10.10.0.2/24 interface=bridge_vpn network=10.10.0.0
add address=192.168.5.101/30 interface=ether5 network=192.168.5.100
add address=192.168.4.102/30 interface=ether4 network=192.168.4.100
add address=192.168.6.101/30 interface=ether3 network=192.168.6.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.5 transport-address=35.10.0.5
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=35.10.0.5/32
add area=backbone network=192.168.5.100/30
add area=backbone network=192.168.4.100/30
add area=backbone network=192.168.6.100/30
/system identity
set name=R01.SPB
```

## R01.MSK:

```
[admin@R01.MSK] > export
/interface bridge
add name=bridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.6
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.6 interface=bridge network=35.10.0.6
add address=192.168.6.102/30 interface=ether4 network=192.168.6.100
add address=192.168.7.101/30 interface=ether3 network=192.168.7.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.6 transport-address=35.10.0.6
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone network=35.10.0.6/32
add area=backbone network=192.168.6.100/30
add area=backbone network=192.168.7.100/30
/system identity
set name=R01.MSK
```

## R01.LBN

```
[admin@R01.LBN] > export
/interface bridge
add name=bridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.7
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.7 interface=bridge network=35.10.0.7
add address=192.168.7.102/30 interface=ether4 network=192.168.7.100
add address=192.168.9.101/30 interface=ether3 network=192.168.9.100
add address=192.168.8.101/30 interface=ether5 network=192.168.8.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.7 transport-address=35.10.0.7
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=35.10.0.7/32
add area=backbone network=192.168.7.100/30
add area=backbone network=192.168.9.100/30
add area=backbone network=192.168.8.100/30
/system identity
set name=R01.LBN
```
