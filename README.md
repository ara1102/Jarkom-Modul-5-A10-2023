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

Lakukan konfigurasi iptables berikut pada node Aura

**script.sh - Aura**

```
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')

iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```

**Keterangan:**

- `ip -4 addr show eth0` = Menampilkan informasi mengenai antarmuka eth0, termasuk alamat IP
- `grep` = mencari pola tertentu pada output sebelumnya
- `-t nat` = Menentukan tabel yang akan diubah, dalam hal ini, tabel nat
- `-A POSTROUTING` =  Menambahkan aturan pada rantai POSTROUTING (setelah paket-paket meninggalkan sistem)
- `--to-source $ETH0_IP` = Mengarahkan paket-paket yang keluar melalui eth0 agar alamat sumbernya diganti dengan alamat IP dari eth0 yang sudah diambil sebelumnya

Lakukan testing ping ke google untuk memastikan bahwa node-node yang lainnya sudah mendapatkan akses keluar

**Testing**
```
ping google.com
```

**Result**
![soal1](/images/soal1/soal1.png)

### Soal 2

Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

**script.sh - Sein/Stark (Web Server)**
```
iptables -F

iptables -A INPUT -p icmp -j ACCEPT

iptables -A INPUT -p tcp --dport 8080 -j ACCEPT

iptables -A INPUT -p tcp -j DROP

iptables -A INPUT -p udp -j DROP
```

**script.sh - SchwerMountain, LaubHills, TurkRegion,GrobeForest (Client)**
```
apt-get update
wait
apt-get install netcat -y
```

**Keterangan:**
- `iptables -F` : menghapus semua rule yang ada

- `iptables -A INPUT -p icmp -j ACCEPT`: menambahkan aturan ke chain INPUT untuk menerima semua paket ICMP (Internet Control Message Protocol)

- `iptables -A INPUT -p tcp --dport 8080 -j ACCEPT`: menambahkan aturan ke chain INPUT untuk menerima koneksi TCP yang menuju ke port 8080.

- `iptables -A INPUT -p tcp -j DROP`: menambahkan aturan ke chain INPUT untuk menolak semua koneksi TCP yang tidak sesuai dengan aturan sebelumnya.

-`iptables -A INPUT -p udp -j DROP` : menambahkan aturan ke chain INPUT untuk menolak semua koneksi UDP


**Testing - Sein/Stark (Web Server)**
```
nc -l -p 8080
```

**Testing - client**
```
nc 10.4.4.2 8080
```

setelah terhubung ke port 8080 coba kirim sesuatu untuk melihat apakah sudah berjalan apa tidak

**Result**
![soal2](/images/soal2/1.png)
![soal2](/images/soal2/2.png)

### Soal 3
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

**script.sh - Revolte/Ritcher (DNS/DHCP Server)**
```
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```

**Keterangan:**
- `iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP`: menambahkan rule pada chain INPUT untuk menolak koneksi ICMP yang lebih dari 3
- `--connlimit-above 3`: menentukan batas koneksi
- `--connlimit-mask 0`: menentukan mask

**Testing - client**
```
ping 10.4.0.6 #IP Ritcher
```

pada hasil dibawah terlihat foto ke empat ping nya tidak berjalan

**Result**
![soal3](/images/soal3/1.png)
![soal3](/images/soal3/2.png)
![soal3](/images/soal3/3.png)
![soal3](/images/soal3/4.png)

### Soal 4
Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

**script.sh - Sein/Stark (Web Server)**
```
iptables -A INPUT -p tcp --dport 22 -s 10.4.4.0/22 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
```

**Keterangan:**
- -s `10.4.4.0/22`: menentukan source IP yang diizinkan pada kali ini adalah subnet `10.4.4.0/22` yaitu di block A10 yang merupakan GrobeForest
- `iptables -A INPUT -p tcp --dport 22 -j DROP`: menambahkan rule pada chain INPUT untuk menolak koneksi TCP pada port 22 yang tidak berasal dari subnet A10

**Testing - Sein/Stark (Web Server)**
```
nc -l -p 22
```

**Testing - client (SchwerMountain dan GrobeForest)**
```
nc 10.4.4.2 -p 22
```

Terlihat pada gambar ke-3 di SchwerMountain komentar yang diberikan tidak muncul 

**Result**
![soal4](/images/soal4/1.png)
![soal4](/images/soal4/2.png)
![soal4](/images/soal4/3.png)

### Soal 5
Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

**script5.sh - Sein/Stark (Web Server)**
```
iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -j DROP
```

**Keterangan:**
- `iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT`: menambahkan rule pada chain INPUT untuk mengizinkan akses ke Web Server pada Senin-Jumat pukul 08.00-16.00
- `iptables -A INPUT -p tcp --dport 80 -j DROP`: menambahkan rule pada chain INPUT untuk menolak akses selain dari aturan yang telah ditentukan

**Testing - Sein/Stark (Web Server)**
```
nc -l -p 80
```

**Testing - Aura**
```
nmap 10.4.4.2 -p 80
```

**Result**
![soal5](/images/soal5/soal5.png)

### Soal 6
Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

**script6.sh - Sein/Stark (Web Server)**
```
iptables -A INPUT -p tcp --dport 22 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -p tcp --dport 22 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
```

**Keterangan:**
- `iptables -A INPUT -p tcp --dport 22 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP`: menambahkan rule pada chain INPUT untuk melarang akses pada hari Senin-Kamis pada jam 12.00-13.00
- `iptables -A INPUT -p tcp --dport 22 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP`: menambahkan rule pada chain INPUT untuk melarang akses pada hari Jumat pada jam 11.00-13.00

**Testing - Sein/Stark (Web Server)**
```
nc -l -p 80
```

**Testing - Aura**
```
nmap 10.4.4.2 -p 80
```

**Result**
![soal6](/images/soal6/1.png)
![soal6](/images/soal6/2.png)

### Soal 7
Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

**script7.sh - Sein/Stark (Web Server)**
```
iptables -A PREROUTING -t nat -p tcp -d 10.4.4.2 --dport 80 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.4.4.2:80
iptables -A PREROUTING -t nat -p tcp -d 10.4.4.2 --dport 80 -j DNAT --to-destination 10.4.0.18:80

iptables -A PREROUTING -t nat -p tcp -d 10.4.0.18 --dport 443 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.4.0.18:443
iptables -A PREROUTING -t nat -p tcp -d 10.4.0.18 --dport 443 -j DNAT --to-destination 10.4.4.2:443
```

**Testing - Aura**
```
curl 10.4.4.2
```

### Soal 8
Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

**script8.sh - Sein/Stark (Web Server)**
```
Subnet_A1="10.4.0.0/30"

start=$(date -d "2023-10-19T00:00" +"%Y-%m-%dT%H:%M")

end=$(date -d "2024-02-15T00:00" +"%Y-%m-%dT%H:%M")

iptables -A INPUT -p tcp -s $Subnet_A1 --dport 80 -m time --datestart "$start" --datestop "$end" -j DROP
```

**Keterangan:**
- `Subnet_A1="10.4.0.0/30"`: mendefinisikan variabel `Subnet_A1` yang merupakan ip subnet A1 yang berisi node Revolte
- `start=$(date -d "2023-10-19T00:00" +"%Y-%m-%dT%H:%M")`: mendefinisikan variabel `start` yang merupakan tanggal mulai pemilu
- `end=$(date -d "2024-02-15T00:00" +"%Y-%m-%dT%H:%M")`: mendefinisikan variabel `end` yang merupakan tanggal selesai pemilu
- `iptables -A INPUT -p tcp -s $Subnet_A1 --dport 80 -m time --datestart "$start" --datestop "$end" -j DROP`: menambahkan rule pada chain INPUT untuk melarang akses di `Subnet_A1` di rentang waktu `start` hingga `end`


**Testing - Sein/Stark (Web Server)**
```
nc -l -p 80
```

**Testing - Aura dan Revolte**
```
nmap 10.4.4.2 -p 80
```

Pada gambar dibawah terlihat bahwa di Revolte memiliki status `filtered` dan pada aura statusnya `open`
**Result**
![soal8](/images/soal8/1.png)
![soal8](/images/soal8/2.png)

### Soal 9
Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)

**script9.sh - Sein/Stark (Web Server)**
```
iptables -N portscan

iptables -A INPUT -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name portscan --update --seconds 600 --hitcount 20 -j DROP

iptables -A INPUT -m recent --name portscan --set -j ACCEPT
iptables -A FORWARD -m recent --name portscan --set -j ACCEPT
```

**Keterangan:**
- `-iptables N portscan` : membuat chain iptables baru dengan nama "portscan" yang akan digunakan untuk menyimpan informasi terkait deteksi port scanning.
- `-m recent --name portscan --update --seconds 600 --hitcount 20` : menggunakan modul recent untuk mendeteksi port scanning. Aturan ini akan melakukan update pada hitcount setiap 600 detik (10 menit) dan jika jumlah percobaan melebihi 20, paket tersebut akan ditolak.

Untuk melakukan testing, kami menggunakan ping terhadap Web Server yaitu Sein

**Testing - client**
```
nmap 10.4.4.2 
```

Disaat packet yang telah terkirim lebih dari 20, maka paket selanjutnya akan langsung di drop.

**Result**
![soal9](/images/soal9/1.png)

### Soal 10
Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 

**script10.sh - Sein/Stark (Web Server)**
```
iptables -I INPUT -m recent --name portscan --update --seconds 600 --hitcount 20 -j LOG --log-prefix "Portscan detected: " --log-level 4

iptables -I FORWARD -m recent --name portscan --update --seconds 600 --hitcount 20 -j LOG --log-prefix "Portscan detected: " --log-level 4
```

melakukan konfigurasi pada `etc/rsyslog.d/50-default.conf` untuk menambahkan configurasi `kernel.warning                  -/var/log/iptables.log`

```
#
# First some standard log files.  Log by facility.
#
auth,authpriv.*                 /var/log/auth.log
*.*;auth,authpriv.none          -/var/log/syslog
#cron.*                         /var/log/cron.log
#daemon.*                       -/var/log/daemon.log
kern.*                          -/var/log/kern.log
kernel.warning                  -/var/log/iptables.log
#lpr.*                          -/var/log/lpr.log
mail.*                          -/var/log/mail.log
#user.*                         -/var/log/user.log

#
# Logging for the mail system.  Split it up so that
# it is easy to write scripts to parse these files.
#
#mail.info                      -/var/log/mail.info
#mail.warn                      -/var/log/mail.warn
mail.err                        /var/log/mail.err
```

Jalankan command
```
touch /var/log/iptables.log
```
dan
```
/etc/init.d/rsyslog restart
```

**Keterangan:**
No 10 memiliki aturan yang hampir sama seperti No 9. Hanya saja terdapat parameter rules `LOG --log-prefix "Portscan detected: " --log-level 4` dengan tujuan untuk mengarahkan paket yang memenuhi aturan untuk dilakukan logging.

- `-j LOG`: melakukan logging
- `--log-prefix "Portscan detected: "`: menambahkan prefix kedalam log yaitu kalimat "Portscan detected: (isi dari log)"
- `--log-level 4`: menentukan tingkatan log pada syslog. Level 4 berarti 'Warning'.

**Testing - client**
```
ping ipwebserver -c 25
```

Disaat packet yang telah terkirim lebih dari 20, maka packet selanjutnya akan langsung di drop.

**Result**
![soal2](/images/soal2/1.png)
![soal2](/images/soal2/2.png)
