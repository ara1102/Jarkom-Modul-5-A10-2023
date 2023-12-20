# Jarkom-Modul-5-A10-2023

## Anggota Kelompok

| NRP        | Name                        |
| ---------- | --------------------------- |
| 5025211081 | Gabriella Natasya Br Ginting|
| 5025211102 | Adhira Riyanti Amanda       |

## Topologi

- Richter adalah DNS Server
- Revolte adalah DHCP Server
- Sein dan Stark adalah Web Server
- Jumlah Host pada SchwerMountain adalah 64
- Jumlah Host pada LaubHills adalah 255
- Jumlah Host pada TurkRegion adalah 1022
- Jumlah Host pada GrobeForest adalah 512

## Rute Subnet

- Subnet
![Subnet](/images/subnet.jpg)

- Rute
![Rute](/images/rute.png)


## Tree
![Tree](/images/tree.jpg)

## Pembagian IP
![Ip](/images/ip.png)

## Konfigurasi
- Aura
```
auto eth0
iface eth0 inet dhcp

#A8
auto eth1
iface eth1 inet static
        address 10.4.0.21
        netmask 255.255.255.252

#A6
auto eth2
iface eth2 inet static
        address 10.4.0.13
        netmask 255.255.255.252

# Heiter
#A10
up route add -net 10.4.4.0 netmask 255.255.252.0 gw 10.4.0.22
#A9
up route add -net 10.4.8.0 netmask 255.255.248.0 gw 10.4.0.22

# Frieren
#A1
up route add -net 10.4.0.0 netmask 255.255.255.252 gw 10.4.0.14
#A2
up route add -net 10.4.0.4 netmask 255.255.255.252 gw 10.4.0.14
#A3
up route add -net 10.4.0.128 netmask 255.255.255.128 gw 10.4.0.14
#A4
up route add -net 10.4.2.0 netmask 255.255.254.0 gw 10.4.0.14
#A5
up route add -net 10.4.0.8 netmask 255.255.255.252 gw 10.4.0.14
#A7
up route add -net 10.4.0.16 netmask 255.255.255.252 gw 10.4.0.14
```

- Heiter
```
#A8
auto eth0
iface eth0 inet static
	address 10.4.0.22
	netmask 255.255.255.252
	gateway 10.4.0.21

#A9
auto eth1
iface eth1 inet static
	address 10.4.8.1
	netmask 255.255.248.0 

#A10
auto eth2
iface eth2 inet static
	address 10.4.4.1
	netmask 255.255.252.0 

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- TurkRegion
```
#A9
auto eth0
iface eth0 inet dhcp
	gateway 10.4.8.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- Sein
```
#A10
auto eth0
iface eth0 inet static
	address 10.4.4.2
	netmask 255.255.252.0 
	gateway 10.4.4.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- GrobeForest
```
#A10
auto eth0
iface eth0 inet dhcp
	gateway 10.4.4.1
	up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- Frieren
```
#A6
auto eth0
iface eth0 inet static
	address 10.4.0.14
	netmask 255.255.255.252
	gateway 10.4.0.13

#A7
auto eth1
iface eth1 inet static
	address 10.4.0.17
	netmask 255.255.255.252

#A5
auto eth2
iface eth2 inet static
	address 10.4.0.9
	netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A1
up route add -net 10.4.0.0 netmask 255.255.255.252 gw 10.4.0.10
#A2
up route add -net 10.4.0.4 netmask 255.255.255.252 gw 10.4.0.10
#A3
up route add -net 10.4.0.128 netmask 255.255.255.128 gw 10.4.0.10
#A4
up route add -net 10.4.2.0 netmask 255.255.254.0 gw 10.4.0.10
```

- Himmel
```
#A5
auto eth0
iface eth0 inet static
	address 10.4.0.10
	netmask 255.255.255.252
	gateway 10.4.0.9

#A4
auto eth1
iface eth1 inet static
	address 10.4.2.1
	netmask 255.255.254.0

#A3
auto eth2
iface eth2 inet static
	address 10.4.0.129
	netmask 255.255.255.128

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A1
up route add -net 10.4.0.0 netmask 255.255.255.252 gw 10.4.0.130
#A2
up route add -net 10.4.0.4 netmask 255.255.255.252 gw 10.4.0.130
```

- LaubHills
```
#A4
auto eth0
iface eth0 inet dhcp
	gateway 10.4.2.1
	up echo nameserver 192.168.122.1 > /etc/resolv.confs
```

- SchwerMountain
```
#A3
auto eth0
iface eth0 inet dhcp
	gateway 10.4.0.129

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- Fern
```
#A3
auto eth0
iface eth0 inet static
	address 10.4.0.130
	netmask 255.255.255.128
	gateway 10.4.0.129

#A2
auto eth1
iface eth1 inet static
	address 10.4.0.5
	netmask 255.255.255.252

#A1
auto eth2
iface eth2 inet static
	address 10.4.0.1
	netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- Richter
```
#A2
auto eth0
iface eth0 inet static
	address 10.4.0.6
	netmask 255.255.255.252
	gateway 10.4.0.5
        up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

- Revolte
```
#A1
auto eth0
iface eth0 inet static
        address 10.4.0.2
        netmask 255.255.255.252
        gateway 10.4.0.1
up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
