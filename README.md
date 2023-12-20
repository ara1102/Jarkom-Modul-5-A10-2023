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

## DHCP

### DHCP Server Set Up
- script.sh pada Revolte
    ```sh
    apt-get update
    wait
    apt-get install isc-dhcp-server -y
    wait

    echo '
    INTERFACESv4="eth0"
    INTERFACESv6=""
    ' > /etc/default/isc-dhcp-server

    echo '
    #A1
    subnet 10.4.0.0 netmask 255.255.255.252 {
    }

    #A2
    subnet 10.4.0.4 netmask 255.255.255.252 {
    }

    #A3
    subnet 10.4.0.128 netmask 255.255.255.128 {
        range 10.4.0.131 10.4.0.254;
        option routers 10.4.0.129;
        option broadcast-address 10.4.0.255;
        default-lease-time 600;
        max-lease-time 7200;
    }

    #A4
    subnet 10.4.2.0 netmask 255.255.254.0 {
        range 10.4.2.2 10.4.3.255; 
        option routers 10.4.2.1;
        option broadcast-address 10.4.2.255;
        default-lease-time 600;
        max-lease-time 7200;
    }

    #A5
    subnet 10.4.0.8 netmask 255.255.255.252 {
    }

    #A6
    subnet 10.4.0.12 netmask 255.255.255.252 {
    }

    #A7
    subnet 10.4.0.16 netmask 255.255.255.252 {
    }

    #A8
    subnet 10.4.0.20 netmask 255.255.255.252 {
    }

    #A9
    subnet 10.4.8.0 netmask 255.255.248.0 {
        range 10.4.8.2 10.4.15.254;
        option routers 10.4.8.1;
        option broadcast-address 10.4.15.255;
        default-lease-time 600;
        max-lease-time 7200;
    }

    #A10
    subnet 10.4.4.0 netmask 255.255.252.0 {
        range 10.4.4.3 10.4.7.254;
        option routers 10.4.4.1;
        option broadcast-address 10.4.7.255;
        default-lease-time 600;
        max-lease-time 7200;
    }
    '>  /etc/dhcp/dhcpd.conf

    service isc-dhcp-server restart
    ```

### DHCP Relay Set Up
- script.sh pada Himmel dan Heiter
    ```sh
    apt-get update
    wait
    apt-get install isc-dhcp-relay -y
    wait

    echo '
    SERVERS="10.4.0.2"
    INTERFACES="eth0 eth1 eth2"
    OPTIONS="-m replace"
    ' >  /etc/default/isc-dhcp-relay

    echo '
    net.ipv4.ip_forward=1
    ' >  /etc/sysctl.conf

    service isc-dhcp-relay restart
    ```

## Soal

### Soal 1

Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

### Soal 2

Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

### Soal 3
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

### Soal 4
Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

### Soal 5
Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

### Soal 6
Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

### Soal 7
Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

### Soal 8
Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

### Soal 9
Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)

### Soal 10
Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 
