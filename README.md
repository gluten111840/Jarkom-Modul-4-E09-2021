# Jarkom-Modul-4-E09-2021

# VLSM

## Penjelasan VLSM

Untuk perhitungan IP dengan menggunakan VLSM, hal yang pertama kita lakukan adalah mengelompokkan setiap PC yang terhubung ke router. Jika terdapat 2 atau lebih PC yang terhubung dengan router namun dengan switch yang sama, maka akan dimasukkan ke dalam 1 kelompok.

Setelah itu, kita menjumlahkan usable IP atau host yang dimiliki oleh masing-masing PC, setiap PC yang terhubung dengan 1 router, maka jumlah hostnya akan ditambahkan dengan 1, dan juga ketika terhubung dengan 2 router, maka jumlah hostnya akan ditambahkan dengan 2, lalu untuk router yang berhubungan dengan router lain, jumlah hostnya adalah 2, karena dia terhubung dengan PC dan juga router lain.

## Pemetaan Subnet A

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled.png)

Lalu direpresentasikan dengan tabel, didapatkan data sebagai berikut.

| Subnet | Netmask | IP | Subnet Mask | Jumlah IP |
| --- | --- | --- | --- | --- |
| A1 (Calmbelt + Courtyard) | /21 | 192.204.0.0 | 255.255.248.0 | 2021 |
| A2 (Jipangu) | /25 | 192.204.27.0 | 255.255.255.128 | 101 |
| A3 (Cipher) | /22 | 192.204.8.0 | 255.255.252.0 | 701 |
| A4 (Enieslobby) | /24 | 192.204.26.0 | 255.255.255.0 | 252 |
| A5 (Pucci + Water7) | /30 | 192.204.27.144 | 255.255.255.252 | 2 |
| A6 (Water7 + Foosha) | /30 | 192.204.27.148 | 255.255.255.252 | 2 |
| A7 (Blueno) | /22 | 192.204.16.0 | 255.255.252.0 | 1001 |
| A8 (Jabra) | /22 | 192.204.12.0 | 255.255.252.0 | 521 |
| A9 (Foosha + Guanhao) | /30 | 192.204.27.152 | 255.255.255.252 | 2 |
| A10 (Guanhao + Oimo) | /30 | 192.204.27.156 | 255.255.255.252 | 2 |
| A11 (Elena) | /22 | 192.204.20.0 | 255.255.252.0 | 721 |
| A12 (Guanhao + Maingate + Alabasta) | /23 | 192.204.24.0 | 255.255.254.0 | 502 |
| A13 (Jorge) | /28 | 192.204.27.128 | 255.255.255.240 | 13 |
| A14 (Doriki) | /30 | 192.204.27.160 | 255.255.255.252 | 2 |
| A15 (Fukurou) | /30 | 192.204.27.164 | 255.255.255.252 | 2 |
| Total | /19 |  | 255.255.224.0 | 5845 |

![image](https://user-images.githubusercontent.com/7587945/143666429-aa44564f-07b8-4404-a669-4f02c4778ad2.png)

Setelah itu, kita menghitung IP dari setiap subnet. Dari jumlah IP keseluruhan, didapatkan sebesar 5845 IP, jika dikonversikan ke dalam Netmask, didapatkan Netmask = /19. Pada tabel di modul, diketahui bahwa Netmask /19 memiliki Wildcard 0.0.31.255, di mana digit ketiga yaitu 31, karena dimulai dari 0, maka range digit ketiga adalah 0 - 31, yang menandakan ada 32 macam untuk digit ketiga. Dalam perhitungan ini, kita menggunakan tree agar mudah. Prefix IP yang kami gunakan adalah 192.204 dengan IP besar 192.204.0.0 /19.

Dari IP 192.204.0.0 /19 ini, kita membagi rangenya menjadi 2 sama rata. Di sisi kiri memiliki range IP 192.204.0.0 /20 hingga 192.204.15.0 /20. Sedangkan di sisi kanan, rangenya adalah 192.204.16.0 /20 hingga 192.204.31.0 /20. Karena pada hasil subnetting tidak ada yang membutuhkan netmask /20, maka kita meneruskan pembagian. Pada sisi kiri, kita membagi 2 sama rata lagi, sehingga menjadi range 192.204.0.0 /21 hingga 192.204.7.0 /21 dan 192.204.8.0 /21 hingga 192.204.15.0 /21.

![image](https://user-images.githubusercontent.com/7587945/143666474-c1ee61ce-2949-4fa5-9500-58a8a710a29c.png)

Diketahui bahwa terdapat 1 subnet yang membutuhkan netmask /21, yaitu subnet A1. Maka kita assign A1 dengan range IP 192.204.0.0 /21 hingga 192.204.7.0 /21, dan menjadikan range tersebut sebagai leave serta tidak perlu dibagi lagi. Setelah itu kita melanjutkan sisi kanan hingga kita mendapatkan semua subnet A mendapatkan IP.

![Modul4 (4).jpg](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Modul4_(4).jpg)  

Dari hasil perhitungan di atas, didapatkan rekap IP setiap subnet sebagai berikut.

| Subnet | Netmask | IP | Subnet Mask | Jumlah IP |
| --- | --- | --- | --- | --- |
| A1 (Calmbelt + Courtyard) | /21 | 192.204.0.0 | 255.255.248.0 | 2021 |
| A2 (Jipangu) | /25 | 192.204.27.0 | 255.255.255.128 | 101 |
| A3 (Cipher) | /22 | 192.204.8.0 | 255.255.252.0 | 701 |
| A4 (Enieslobby) | /24 | 192.204.26.0 | 255.255.255.0 | 252 |
| A5 (Pucci + Water7) | /30 | 192.204.27.144 | 255.255.255.252 | 2 |
| A6 (Water7 + Foosha) | /30 | 192.204.27.148 | 255.255.255.252 | 2 |
| A7 (Blueno) | /22 | 192.204.16.0 | 255.255.252.0 | 1001 |
| A8 (Jabra) | /22 | 192.204.12.0 | 255.255.252.0 | 521 |
| A9 (Foosha + Guanhao) | /30 | 192.204.27.152 | 255.255.255.252 | 2 |
| A10 (Guanhao + Oimo) | /30 | 192.204.27.156 | 255.255.255.252 | 2 |
| A11 (Elena) | /22 | 192.204.20.0 | 255.255.252.0 | 721 |
| A12 (Guanhao + Maingate + Alabasta) | /23 | 192.204.24.0 | 255.255.254.0 | 502 |
| A13 (Jorge) | /28 | 192.204.27.128 | 255.255.255.240 | 13 |
| A14 (Doriki) | /30 | 192.204.27.160 | 255.255.255.252 | 2 |
| A15 (Fukurou) | /30 | 192.204.27.164 | 255.255.255.252 | 2 |
| Total | /19 |  | 255.255.224.0 | 5845 |

# CIDR

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%201.png)

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%202.png)

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%203.png)

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%204.png)

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%205.png)

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%206.png)

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%207.png)

Tree

![modul4 (1).jpg](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/modul4_(1).jpg)

Tabel

| Subnet | Netmask | IP | Subnet Mask |
| --- | --- | --- | --- |
| A1 | /21 | 192.205.0.0 | 255.255.248.0 |
| A2 | /25 | 192.205.8.0 | 255.255.255.128 |
| A3 | /22 | 192.204.32.0 | 255.255.252.0 |
| A4 | /24 | 192.204.4.0 | 255.255.255.0 |
| A5 | /30 | 192.205.16.0 | 255.255.255.252 |
| A6 | /30 | 192.205.64.0 | 255.255.255.252 |
| A7 | /22 | 192.205.128.0 | 255.255.252.0 |
| A8 | /22 | 192.204.36.0 | 255.255.252.0 |
| A9 | /30 | 192.204.64.0 | 255.255.255.252 |
| A10 | /30 | 192.204.8.0 | 255.255.255.252 |
| A11 | /22 | 192.204.0.0 | 255.255.252.0 |
| A12 | /23 | 192.204.32.0 | 255.255.254.0 |
| A13 | /28 | 192.204.34.0 | 255.255.255.240 |
| A14 | /30 | 192.204.128.0 | 255.255.255.252 |
| A15 | /30 | 192.204.16.0 | 255.255.255.252 |
|  |  |  |  |

# Pucci

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.205.16.2
netmask 255.255.255.252
gateway 192.205.16.1

auto eth1
iface eth1 inet static
address 192.205.8.1
netmask 255.255.255.128

auto eth2
iface eth2 inet static
address 192.205.0.1
netmask 255.255.248.0
```

### Routing

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.205.16.1
```

# Jipangu

```jsx
auto eth0
iface eth0 inet static
address 192.205.8.2
netmask 255.255.255.128
gateway 192.205.8.1
```

# Courtyard

```jsx
auto eth0
iface eth0 inet static
address 192.205.0.3
netmask 255.255.248.0
gateway 192.205.0.1
```

# Calmbelt

```jsx
auto eth0
iface eth0 inet static
address 192.205.0.2
netmask 255.255.248.0
gateway 192.205.0.1
```

# Water7

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.205.64.2
netmask 255.255.255.252
gateway 192.205.64.1

auto eth1
iface eth1 inet static
address 192.205.32.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 192.205.16.1
netmask 255.255.255.252
```

### Routing

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.205.64.1
route add -net 192.205.0.0 netmask 255.255.248.0 gw 192.205.16.2
route add -net 192.205.8.0 netmask 255.255.255.128 gw 192.205.16.2
```

# Cipher

```jsx
auto eth0
iface eth0 inet static
address 192.205.32.2
netmask 255.255.252.0
gateway 192.205.32.1
```

# Seastone

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.204.4.3
netmask 255.255.255.0
gateway 192.204.4.1

auto eth1
iface eth1 inet static
address 192.204.0.1
netmask 255.255.252.0
```

### Routing

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.204.4.1
```

# Elena

```jsx
auto eth0
iface eth0 inet static
address 192.204.0.2
netmask 255.255.252.0
gateway 255.255.252.1
```

# Oimo

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.204.8.2
netmask 255.255.255.252
gateway 192.204.8.1

auto eth1
iface eth1 inet static
address 192.204.4.1
netmask 255.255.255.0

auto eth2
iface eth2 inet static
address 192.204.16.1
netmask 255.255.255.252
```

### Routing

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.204.8.1
route add -net 192.204.0.0 netmask 255.255.252.0 gw 192.204.4.3
```

# EniesLobby

```jsx
auto eth0
iface eth0 inet static
address 192.204.4.2
netmask 255.255.255.0
gateway 192.204.4.1
```

# Fukurou

```jsx
auto eth0
iface eth0 inet static
address 192.204.16.2
netmask 255.255.254.0
gateway 192.204.16.1
```

# Alabasta

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.204.32.2
netmask 255.255.254.0
gateway 192.204.32.1

auto eth1
iface eth1 inet static
address 192.204.34.1
netmask 255.255.255.240
```

### Routing

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.204.32.1
```

# Jorge

```jsx
auto eth0
iface eth0 inet static
address 192.204.34.2
netmask 255.255.255.240
gateway 192.204.34.1
```

# Guanhao

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.204.64.2
netmask 255.255.255.252
gateway 192.204.64.1

auto eth1
iface eth1 inet static
address 192.204.36.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 192.204.8.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 192.204.32.1
netmask 255.255.254.0
```

### Routing

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.204.64.1
route add -net 192.204.0.0 netmask 255.255.252.0 gw 192.204.8.2
route add -net 192.204.4.0 netmask 255.255.255.0 gw 192.204.8.2
route add -net 192.204.16.0 netmask 255.255.254.0 gw 192.204.8.2
route add -net 192.204.34.0 netmask 255.255.255.240 gw 192.204.32.2
```

# Maingate

```jsx
auto eth0
iface eth0 inet static
address 192.204.32.3
netmask 255.255.254.0
gateway 192.204.32.1
```

# Jabra

```jsx
auto eth0
iface eth0 inet static
address 192.204.36.2
netmask 255.255.252.0
gateway 192.204.36.1
```

# Foosha

```jsx
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 192.205.128.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 192.204.128.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 192.205.64.1
netmask 255.255.255.252

auto eth4
iface eth4 inet static
address 192.204.64.1
netmask 255.255.255.252
```

### Routing

```bash
route add -net 192.205.0.0 netmask 255.255.248.0 gw 192.205.64.2
route add -net 192.205.8.0 netmask 255.255.255.128 gw 192.205.64.2
route add -net 192.205.16.0 netmask 255.255.255.252 gw 192.205.64.2
route add -net 192.205.32.0 netmask 255.255.252.0 gw 192.205.64.2
route add -net 192.204.36.0 netmask 255.255.252.0 gw 192.204.64.2
route add -net 192.204.8.0 netmask 255.255.255.252 gw 192.204.64.2
route add -net 192.204.32.0 netmask 255.255.254.0 gw 192.204.64.2
route add -net 192.204.34.0 netmask 255.255.255.240 gw 192.204.64.2
route add -net 192.204.4.0 netmask 255.255.255.0 gw 192.204.64.2
route add -net 192.204.0.0 netmask 255.255.252.0 gw 192.204.64.2
route add -net 192.204.16.0 netmask 255.255.254.0 gw 192.204.64.2
```

# Doriki

```jsx
auto eth0
iface eth0 inet static
address 192.204.128.2
netmask 255.255.255.252
gateway 192.204.128.1
```

# Blueno

```jsx
auto eth0
iface eth0 inet static
address 192.205.128.2
netmask 255.255.252.0
gateway 192.205.128.1
```
