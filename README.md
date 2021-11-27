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

Lalu untuk melakukan testing, kita memasukkan semua IP dan netmask ke dalam Cisco Packet Tracer yang telah dipersiapkan sebelumnya.
![testing vlsm](https://user-images.githubusercontent.com/81345045/143670863-f71489db-e86d-4bdc-9451-f7ae2029c323.png) \
Dengan detail config IP dan routing sebagai berikut

## Jipangu
![Jipangu 1](https://user-images.githubusercontent.com/81345045/143670916-29999d65-cff0-4c33-8371-95a93a4525a0.png) 
## Courtyard
![Courtyard 1](https://user-images.githubusercontent.com/81345045/143671682-5da62ee7-1421-44bf-8993-36008e42d574.png) 
## Calmbelt
![Calmbelt 1](https://user-images.githubusercontent.com/81345045/143671691-3ef9f5e3-83aa-4952-902a-d2d9c4d1d129.png) 
## Pucci
![Pucci 1](https://user-images.githubusercontent.com/81345045/143671755-2fb8938b-cb04-4eed-97b6-ffcfba8d8ce8.png) \
![Pucci 2](https://user-images.githubusercontent.com/81345045/143671767-e2b94874-9ecf-45fe-9de2-a7b9987f34ec.png) \
![Pucci 3](https://user-images.githubusercontent.com/81345045/143671794-14fd5036-ed0c-445a-a4b4-834c60e0f93c.png) \
![Pucci 4](https://user-images.githubusercontent.com/81345045/143671804-ca2b2568-7fd8-48df-abed-8c4580431a54.png) 
## Cipher
![Cipher](https://user-images.githubusercontent.com/81345045/143671856-0043bf4a-c6b1-4a26-a08d-09711177fa16.png) 
## Water7
![Water7 1](https://user-images.githubusercontent.com/81345045/143671912-3569fbbe-c337-46f6-8af3-40044c9fcec3.png) \
![Water7 2](https://user-images.githubusercontent.com/81345045/143671932-12bdfd2e-689a-47d5-91e0-77cc640c4584.png) \
![Water7 3](https://user-images.githubusercontent.com/81345045/143671945-073b3096-ac9d-4cd3-a5b1-34ce1baf1d55.png) \
![Water7 4](https://user-images.githubusercontent.com/81345045/143671976-32346756-6626-4c42-92c9-0c359fa415d8.png) 
## Elena
![Elena 1](https://user-images.githubusercontent.com/81345045/143672062-b71f931f-4b09-480e-b8c9-41e7fe990078.png) 
## Seastone
![Seastone 1](https://user-images.githubusercontent.com/81345045/143672900-c623868f-4cb3-4c8d-bdd8-4387438348d4.png) \
![Seastone 2](https://user-images.githubusercontent.com/81345045/143672920-6168b1cb-6ca9-4599-aab3-2bc6bdbe5303.png) \
![Seastone 3](https://user-images.githubusercontent.com/81345045/143672953-084c7e03-75af-48bb-9fd0-9061f2876aee.png) \
![Seastone 4](https://user-images.githubusercontent.com/81345045/143672959-1db4884e-2c4d-42fb-a449-82cb7caf83ca.png) 
## EniesLobby
![EniesLobby 1](https://user-images.githubusercontent.com/81345045/143672977-140912bf-3bca-4fa1-86a4-e6b103a6a7d9.png) 
## Fukurou
![Fukurou 1](https://user-images.githubusercontent.com/81345045/143673002-b9f8c905-65c1-4130-8d48-49a264391c81.png) 
## Oimo
![Oimo 1](https://user-images.githubusercontent.com/81345045/143673018-b1253058-cb63-417b-9f7e-7dd8a422e667.png) \
![Oimo 2](https://user-images.githubusercontent.com/81345045/143673028-3d900d69-7ba0-423c-9422-71e656ac5eae.png) \
![Oimo 3](https://user-images.githubusercontent.com/81345045/143673071-debac06d-9eb7-4a58-a82c-2b8510112d32.png) \
![Oimo 4](https://user-images.githubusercontent.com/81345045/143673084-72c31b09-ee9e-4246-8ad9-d5e197e14c13.png) 
## Jorge
![Jorge 1](https://user-images.githubusercontent.com/81345045/143673111-1491ac7e-3097-4f4a-801e-8440de4fb6ae.png) 
## Alabasta
![Alabasta 1](https://user-images.githubusercontent.com/81345045/143673129-182eaaf9-6ca4-4cef-a970-a1038ff22152.png) \
![Alabasta 2](https://user-images.githubusercontent.com/81345045/143673151-d61d29ed-c4a1-4ba5-839a-f0747be0b164.png) \
![Alabasta 3](https://user-images.githubusercontent.com/81345045/143673181-c8c6afb1-857f-4521-84d7-f8d996a1582f.png) 
## Maingate
![Maingate 1](https://user-images.githubusercontent.com/81345045/143673691-ce1fe128-46e4-46ee-ab07-542e761a1e56.png) 
## Jabra
![Jabra 1](https://user-images.githubusercontent.com/81345045/143673726-32e8de5d-f61b-4a88-9a68-cf634a57eea4.png) 
## Guanhao
![Guanhao 1](https://user-images.githubusercontent.com/81345045/143673756-e7bcae1d-9f25-4a44-8399-96112463abad.png) \
![Guanhao 2](https://user-images.githubusercontent.com/81345045/143673769-77aa7311-a8d8-474c-81ce-0b7e4bda62be.png) \
![Guanhao 3](https://user-images.githubusercontent.com/81345045/143673779-33e6e250-678d-4581-920f-9c76b659c5b2.png) \
![Guanhao 4](https://user-images.githubusercontent.com/81345045/143673827-3395db98-6c1f-4c7b-95ea-8672a2372da8.png) \
![Guanhao 5](https://user-images.githubusercontent.com/81345045/143673839-6b6f96cf-d83e-4851-bada-758605b808bb.png)  
## Blueno
![Blueno 1](https://user-images.githubusercontent.com/81345045/143673882-9393c081-fbc5-4f16-a4e4-da535f9304a2.png) 
## Doriki
![Doriki 1](https://user-images.githubusercontent.com/81345045/143673895-df0df7b0-55d7-40cb-b037-0e7a3b3cff26.png) 
## Foosha
![Foosha 1](https://user-images.githubusercontent.com/81345045/143673902-814774a7-9b18-4b73-b2b4-a552fcd8224d.png) \
![Foosha 2](https://user-images.githubusercontent.com/81345045/143673934-34de7a91-f98f-424e-8725-6bc04b7cfdfc.png) \
![Foosha 3](https://user-images.githubusercontent.com/81345045/143673947-65578a29-c852-48bc-bc5c-37ec5d973fd1.png) \
![Foosha 4](https://user-images.githubusercontent.com/81345045/143673956-014e52a0-499f-4fc4-9ee2-d662e7e69018.png) \
![Foosha 5](https://user-images.githubusercontent.com/81345045/143673977-4993882f-c972-4173-9e63-2f5ed2cb25ba.png) \
![Foosha 6](https://user-images.githubusercontent.com/81345045/143673986-61864654-b59b-48d9-a88d-18330d4fbceb.png) \
![Foosha 7](https://user-images.githubusercontent.com/81345045/143673995-c5fc2908-5c39-4a33-a715-4251f1389622.png) 
# Test PING antar PC, Router, dan Server
## Jipangu -> Jorge
![Jipangu Jorge](https://user-images.githubusercontent.com/81345045/143674044-66bb43b3-6adb-43b9-8fb4-00e6309f6e98.png) 
## Oimo -> Pucci
![Oimo Pucci](https://user-images.githubusercontent.com/81345045/143674060-28a46051-f33d-4f5a-8a3d-e78a89bf009d.png) 
## Chiper -> Fukurou
![Cipher Fukurou](https://user-images.githubusercontent.com/81345045/143674088-4d9b5cb1-ad9f-46ac-8543-009347b5f17a.png) 
## Fukurou -> Doriki
![Fukurou Doriki](https://user-images.githubusercontent.com/81345045/143674100-4fd85945-df1e-4dbd-b33d-0e4bef5c059e.png) 

# CIDR
Pada metode CIDR ini, kita mengelompokkan subnet A yang memiliki anggota yang sama dengan metode VLSM. Untuk pengelompokan, kita mengelompokkan antarsubnet yang terhubung dengan 1 router yang sama dan dimulai dari node terluar.
Untuk subnet B, pengelompokan adalah sebagai berikut:
1.	B1 /20 → A2 /25 + A1 /21
2.	B2 /21 → A4 /24 + A11 /22
3.	B3 /22 → A12 /23 + A12 /28

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%201.png)
Subnet C :
1.	C1 /19 → B1 /20 + A5 /30
2.	C2 /20 → B2 /21 + A10 /30
3.	C3 /21 → B3 /22 + A8 /22

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%202.png)
Subnet D :
1.	D1 /18 → C1 /19 + A3 /22
2.	D2 /19 → C2 /20 + A10 /30

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%203.png)
Subnet E :
1.	E1 /17 → D1 /18 + A6 /30
2.	E2 /18 → D2 /19 + C3 /21

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%204.png)
Subnet F :
1.	F1 /16 → E1 /17 + A7 /22
2.	F2 /17 → E2 /18 + A9 /30

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%205.png)
Subnet G :
1.	G1 /16 → F2 /17 + A14 /30

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%206.png)
Subnet H :
1.	H1 /15 → F1 /16 + G1 /16

![Untitled](Jarkom-Modul-4-E09-2021%204710b6be85a44793869125203c80a906/Untitled%207.png)

Setelah itu kita melakukan perhitungan dengan menggunakan tree dengan IP besar 192.204.0.0 /15. Lalu membagi 2 sama rata antara sisi kiri dan sisi kanan. Di mana netmask /15 memiliki wildcard 0.1.255.255 yang menandakan bahwa digit kedua memiliki range 0 hingga 1, sehingga di sisi kiri IP-nya menjadi 192.204.0.0 /16 di mana diassign ke subnet G1 yang memiliki netmask /16. Lalu di sisi kanan, memiliki IP 192.205.0.0 /16. Lalu kita membagi lagi hingga sama rata dan didapatkan seluruh subnet memiliki IP masing-masing. Berikut adalah tree yang dihasilkan :
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

Lalu kita memasukkan config IP dan routing ke dalam GNS3 sesuai dengan config di bawah ini : \
n.b. Semua PC dimasukkan ```nameserver 192.168.122.1``` ke dalam /etc/resolv.conf.

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

# Testing PING
## Jipangu -> Jorge
![jipangu jorge cidr](https://user-images.githubusercontent.com/81345045/143674138-24892181-aaaf-4180-b95d-db90bb7953a3.png) 
## Oimo -> Pucci
![oimo pucci cidr](https://user-images.githubusercontent.com/81345045/143674152-fb1e6066-92c4-48f9-9e18-646e44401161.png) 
## Cipher -> Fukurou
![cipher fukurou cidr](https://user-images.githubusercontent.com/81345045/143674166-8ba3cebb-4828-48ec-a9a2-2d58137ea237.png) 
## Fukurou -> Doriki
![fukurou doriki cidr](https://user-images.githubusercontent.com/81345045/143674171-78b1cb95-a5f5-4b03-8eea-bfce88073daf.png) 
## Blueno -> my.its.ac.id
![blueno my its](https://user-images.githubusercontent.com/81345045/143674227-b519b392-4eda-46b1-af20-9d29dd64870f.png) 
## Chiper -> my.its.ac.id
![cipher my its](https://user-images.githubusercontent.com/81345045/143674259-fd267e7e-9444-4d37-aab3-07695766a6a3.png) 
