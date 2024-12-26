## R01.NY

```
[admin@R01.NY] > export
/interface bridge
add name=bridgeloop
add name=vpls protocol-mode=none
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default as=65500 router-id=35.10.0.1
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.1
/interface bridge port
add bridge=vpls interface=ether3
/interface vpls bgp-vpls
add bridge=vpls export-route-targets=1:2 import-route-targets=1:2 name=vpls route-distinguisher=1:2 site-id=6
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.1 interface=bridgeloop network=35.10.0.1
add address=192.168.2.101/30 interface=ether4 network=192.168.2.100
add address=192.168.1.102/30 interface=ether3 network=192.168.1.100
add address=10.10.0.10/24 interface=vpls network=10.10.0.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.1 transport-address=35.10.0.1
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing bgp instance vrf
add redistribute-connected=yes redistribute-ospf=yes routing-mark=vrf1
/routing bgp peer
add address-families=l2vpn name=peer1 remote-address=35.10.0.2 remote-as=65500 update-source=bridgeloop
/routing ospf network
add area=backbone network=192.168.2.100/30
add area=backbone network=192.168.1.100/30
add area=backbone network=35.10.0.1/32
/system identity
set name=R01.NY
```

## R01.LND

```
[admin@R01.LND] > export
/interface bridge
add name=bridgeloop
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default as=65500 router-id=35.10.0.2
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.2 interface=bridgeloop network=35.10.0.2
add address=192.168.2.102/30 interface=ether3 network=192.168.2.100
add address=192.168.3.101/30 interface=ether4 network=192.168.3.100
add address=192.168.7.101/30 interface=ether5 network=192.168.7.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.2 transport-address=35.10.0.2
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing bgp peer
add address-families=vpnv4 name=peer1 remote-address=35.10.0.1 remote-as=65500 update-source=bridgeloop
add address-families=vpnv4 name=peer2 remote-address=35.10.0.3 remote-as=65500 route-reflect=yes update-source=bridgeloop
add address-families=vpnv4 name=peer3 remote-address=35.10.0.4 remote-as=65500 route-reflect=yes update-source=bridgeloop
/routing ospf network
add area=backbone network=192.168.2.100/30
add area=backbone network=192.168.3.100/30
add area=backbone network=192.168.7.100/30
add area=backbone network=35.10.0.2/32
/system identity
set name=R01.LND
```

## R01.HKI

```
[admin@R01.HKI] > export
/interface bridge
add name=bridgeloop
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default as=65500 router-id=35.10.0.3
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.3 interface=bridgeloop network=35.10.0.3
add address=192.168.6.102/30 interface=ether3 network=192.168.6.100
add address=192.168.7.102/30 interface=ether4 network=192.168.7.100
add address=192.168.8.101/30 interface=ether5 network=192.168.8.101
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.3 transport-address=35.10.0.3
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing bgp peer
add address-families=vpnv4 name=peer1 remote-address=35.10.0.6 remote-as=65500 update-source=bridgeloop
add address-families=vpnv4 name=peer2 remote-address=35.10.0.2 remote-as=65500 route-reflect=yes update-source=bridgeloop
add address-families=vpnv4 name=peer3 remote-address=35.10.0.4 remote-as=65500 route-reflect=yes update-source=bridgeloop
/routing ospf network
add area=backbone network=192.168.6.100/30
add area=backbone network=192.168.7.100/30
add area=backbone network=192.168.8.100/30
add area=backbone network=35.10.0.3/32
/system identity
set name=R01.HKI
```

## R01.SPB:

```
[admin@R01.SPB] > export
/interface bridge
add name=bridgeloop
add name=vpls protocol-mode=none
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default as=65500 router-id=35.10.0.6
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.6
/interface bridge port
add bridge=vpls interface=ether4
/interface vpls bgp-vpls
add bridge=vpls export-route-targets=1:2 import-route-targets=1:2 name=vpls route-distinguisher=1:2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.6 interface=bridgeloop network=35.10.0.6
add address=10.10.0.2/24 interface=vpls network=10.10.0.0
add address=192.168.8.102/30 interface=ether3 network=192.168.8.100
add address=192.168.9.101/30 interface=ether4 network=192.168.9.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.6 transport-address=35.10.0.6
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing bgp instance vrf
add redistribute-connected=yes redistribute-ospf=yes routing-mark=vrf1
/routing bgp peer
add address-families=vpnv4 name=peer1 remote-address=35.10.0.3 remote-as=65500 update-source=bridgeloop
/routing ospf network
add area=backbone network=192.168.8.100/30
add area=backbone network=192.168.9.100/30
add area=backbone network=35.10.0.6/32
/system identity
set name=R01.SPB
```

## R01.SVL:

```
[admin@R01.SVL] > export
/interface bridge
add name=bridgeloop
add name=vpls protocol-mode=none
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default as=65500 router-id=35.10.0.5
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.5
/interface bridge port
add bridge=vpls interface=ether4
/interface vpls bgp-vpls
add bridge=vpls export-route-targets=1:2 import-route-targets=1:2 name=vpls route-distinguisher=1:2 site-id=4
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.5 interface=bridgeloop network=35.10.0.5
add address=192.168.4.102/30 interface=ether3 network=192.168.4.100
add address=192.168.5.101/30 interface=ether4 network=192.168.5.100
add address=10.10.0.20/24 interface=vpls network=10.10.0.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.5 transport-address=35.10.0.5
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing bgp instance vrf
add redistribute-connected=yes redistribute-ospf=yes routing-mark=vrf1
/routing bgp peer
add address-families=vpnv4 name=peer1 remote-address=35.10.0.4 remote-as=65500 update-source=bridgeloop
/routing ospf network
add area=backbone network=192.168.4.100/30
add area=backbone network=192.168.5.100/30
add area=backbone network=35.10.0.5/32
/system identity
set name=R01.SVL
```

## R01.LBN

```
[admin@R01.LBN] > export
/interface bridge
add name=bridgeloop
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default as=65500 router-id=35.10.0.4
/routing ospf instance
set [ find default=yes ] router-id=35.10.0.4
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=35.10.0.4 interface=bridgeloop network=35.10.0.4
add address=192.168.3.102/30 interface=ether3 network=192.168.3.100
add address=192.168.4.101/30 interface=ether4 network=192.168.4.100
add address=192.168.6.101/30 interface=ether5 network=192.168.6.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=35.10.0.4 transport-address=35.10.0.4
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing bgp peer
add address-families=vpnv4 name=peer1 remote-address=35.10.0.5 remote-as=65500 update-source=bridgeloop
add address-families=vpnv4 name=peer2 remote-address=35.10.0.3 remote-as=65500 route-reflect=yes update-source=bridgeloop
add address-families=vpnv4 name=peer3 remote-address=35.10.0.2 remote-as=65500 route-reflect=yes update-source=bridgeloop
/routing ospf network
add area=backbone network=192.168.3.100/30
add area=backbone network=192.168.4.100/30
add area=backbone network=192.168.6.100/30
add area=backbone network=35.10.0.4/32
/system identity
set name=R01.LBN
```
