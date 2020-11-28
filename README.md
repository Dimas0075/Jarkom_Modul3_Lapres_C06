# Jarkom_Modul3_Lapres_C06
## Anggota Kelompok :
* Nugroho Dimas Ardiyanto - 05111840000075
* Zakiya Azizah Cahyaningtyas - 05111840000080

### Soal 1. Membuat topologi jaringan demi kelancaran TA-nya dengan kriteria sebagai berikut:
![Soal 1](https://user-images.githubusercontent.com/49650266/100515858-b6285100-31b1-11eb-9989-bfe520acc21f.png)
br

### Soal 2. SURABAYA ditunjuk sebagai perantara (DHCP Relay) antara DHCP Server dan client.
Install dulu “apt-get install isc-dhcp-server” <br>
nano /etc/default/isc-dhcp-server<br>
Lalu atur konfigurasi seperti gambar dibawah <br>
![Soal 2](https://user-images.githubusercontent.com/49650266/100515873-f12a8480-31b1-11eb-9e99-09149ee4a393.png) <br>

### Soal 3-6. Client pada subnet 1 mendapatkan range IP dari 192.168.0.10 sampai 192.168.0.100 dan 192.168.0.110 sampai 192.168.0.200. .Client pada subnet 3 mendapatkan range IP dari 192.168.1.50 sampai 192.168.1.70..Client mendapatkan DNS Malang dan DNS 202.46.129.2 dari DHCP. Client di subnet 1 mendapatkan peminjaman alamat IP selama 5 menit, sedangkan (6) client pada subnet 3 mendapatkan peminjaman IP selama 10 menit.
Menentukan interface eth0 dipilih untuk diberikan layanan DHCP. Konfigurasi pada DHCP Server seperti gambar dibawah. <br>
![Soal 3](https://user-images.githubusercontent.com/49650266/100515959-d9073500-31b2-11eb-82ec-a679189abb0c.png) <br>
<br>
Konfigurasi pada DHCP server untuk gateaway serta menjadikan ip dari server fixed <br>
![Soal3konf](https://user-images.githubusercontent.com/49650266/100515961-da386200-31b2-11eb-8248-8ac119013fcd.png) <br>
<br>
Konfigurasi pada masing-masing subnet untuk mendapatkan Peminjaman IP, DNS Server serta waktu peminjamannya <br>
![Soal 3 Subnet](https://user-images.githubusercontent.com/49650266/100515962-dad0f880-31b2-11eb-9695-21750106ee2a.png) <br>
<br>
Contoh beberapa hasil test di client : <br>
##### Gresik <br>
![Gresik](https://user-images.githubusercontent.com/49650266/100516028-5af75e00-31b3-11eb-8ef4-edf3ed5a74c2.png) <br>
##### Banyuwangi <br>
![banyuwangi](https://user-images.githubusercontent.com/49650266/100516025-58950400-31b3-11eb-9559-11af50431e80.png) <br>
<br>

### Soal 7. User autentikasi milik Anri memiliki format: ● User : userta_yyy ● Password : inipassw0rdta_yyy Keterangan : yyy adalah nama kelompok masing-masing.
Langkah pertama yaitu Install “apt-get install apache2-utils” <br>
Buat user dan password baru, ketikkan htpasswd -c /etc/squid3/passwd userta_c06 <br>
![Soal 7 1](https://user-images.githubusercontent.com/49650266/100516080-c93c2080-31b3-11eb-83e0-f791bf9eae21.jpg) <br>
New password “inipassw0rdta_c06” kemudian re-type <br>
Kemudian agar akses proxy hanya bisa dilakukan oleh anri sebagai user tambahkan <br>
![Soal 7 2](https://user-images.githubusercontent.com/49650266/100516077-c6d9c680-31b3-11eb-9dcb-1dba33831062.png) <br>
###### Hasil : <br>
![Soal 7 3](https://user-images.githubusercontent.com/49650266/100516079-c80af380-31b3-11eb-98d3-b78b6a523393.png)
<br>

### Soal 8. Setiap hari Selasa-Rabu pukul 13.00-18.00. Bu Meguri membatasi penggunaan internet Anri hanya pada jadwal yang telah ditentukan itu saja. Maka diluar jam tersebut, Anri tidak dapat mengakses jaringan internet dengan proxy tersebut. Jadwal bimbingan dengan Bu Meguri adalah
Konfigurasi pada squid.conf untuk menentukan waktu aksesnya. <br>
![Soal 8 1](https://user-images.githubusercontent.com/49650266/100516170-99414d00-31b4-11eb-9d3e-196547f73a30.png) <br>
###### Hasil : <br>
![Soal 8 2](https://user-images.githubusercontent.com/49650266/100516168-98102000-31b4-11eb-812d-5c4fec41da6c.png) <br>
<br>

### Soal 9. Setiap hari Selasa-Kamis pukul 21.00 - 09.00 keesokan harinya (sampai Jumat jam 09.00). Agar Anri bisa fokus mengerjakan TA.
Sama seperti sebelum hanya seperti ini: <br>
acl Peak time SFA 09:00-21:00 <br>
http_access deny Peak <br> <br>
![Soal 9](https://user-images.githubusercontent.com/49650266/100516206-e4f3f680-31b4-11eb-90ff-47472657b234.png) <br>
<br>

### Soal 10. Setiap dia mengakses google.com, maka akan di redirect menuju monta.if.its.ac.id agar Anri selalu ingat untuk mengerjakan TA🙂. Untuk menandakan bahwa Proxy Server ini adalah Proxy yang dibuat oleh Anri.
Lakukan konfigurasi pada squid.conf seperti gambar dibawah : <br>
<br>
![Soal 10](https://user-images.githubusercontent.com/49650266/100516254-31d7cd00-31b5-11eb-8751-8cdefe8e4c6d.png)
<br>

### Soal 11. Bu Meguri meminta Anri untuk mengubah error page default squid
Download file ERR_ACCESS_DENIED terlebih dahulu lalu copy ke /usr/share/squid/errors/templates. Setelah itu error_directory nya diarahkan ke directory tadi. <br> <br>
![Soal 11 1](https://user-images.githubusercontent.com/49650266/100516318-aad72480-31b5-11eb-8f50-4924938a2c21.png) <br>
##### Hasil :
![Soal 11 2](https://user-images.githubusercontent.com/49650266/100516319-ac085180-31b5-11eb-9bad-d6b607bafae2.png) <br>
<br>

### Soal 12. Karena Bu Meguri dan Anri adalah tipe orang pelupa, maka untuk memudahkan mereka, Anri memiliki ide ketika menggunakan proxy cukup dengan mengetikkan domain janganlupa-ta.yyy.pw dan memasukkan port 8080. Keterangan : yyy adalah nama kelompok masing-masing. Contoh: janganlupa-ta.c01.pw
Setting dns di MALANG agar janganlupa-ta.c06.pw mengarah ke MOJOKERTO. <br>
![Soal 12 1](https://user-images.githubusercontent.com/49650266/100516395-2cc74d80-31b6-11eb-8123-76d513302f8a.png)
<br>
![Soal 12 2](https://user-images.githubusercontent.com/49650266/100516389-2afd8a00-31b6-11eb-8fac-5e4f20dd4687.png)
<br>
Coba ping ke janganlupa-ta.c06.pw untuk memastika apakah sudah mengarah ke MOJOKERTO. <br> <br>
![Soal 12 3](https://user-images.githubusercontent.com/49650266/100516391-2b962080-31b6-11eb-99e7-7fe0bbe742c0.png)
<br>
Setting proxy. <br> <br>
![Soal 12 4](https://user-images.githubusercontent.com/49650266/100516393-2cc74d80-31b6-11eb-95c9-b381674731d8.png)









