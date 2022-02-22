# OpenStack Xena : Konfigurasikan Keystone #1

Instal dan Konfigurasi Layanan Identitas OpenStack (Keystone).
Contoh ini didasarkan pada lingkungan seperti berikut.
<pre>
        eth0|10.0.0.30
+-----------+-----------+
| [ Simpul Kontrol ] |
| |
| MariaDB RabbitMQ |
| Memcache httpd |
| Batu Kunci |
+-----------------------+</pre>

## [1] Tambahkan Pengguna dan Database di MariaDB untuk Keystone.
<pre>
root@dlp:~#mysql
Selamat datang di monitor MariaDB. Perintah diakhiri dengan ; atau \g.
ID koneksi MariaDB Anda adalah 36
Versi server: 10.3.31-MariaDB-0ubuntu0.20.04.1 Ubuntu 20.04

Hak Cipta (c) 2000, 2018, Oracle, MariaDB Corporation Ab, dan lainnya.

Ketik 'bantuan;' atau '\h' untuk bantuan. Ketik '\c' untuk menghapus pernyataan input saat ini.

MariaDB [(none)]> buat database keystone;
Kueri OK, 1 baris terpengaruh (0,00 detik)

MariaDB [(none)]> berikan semua hak istimewa pada keystone.* ke keystone@'localhost' yang diidentifikasi oleh 'password';
Kueri OK, 0 baris terpengaruh (0,00 detik)

MariaDB [(none)]> berikan semua hak istimewa pada keystone.* ke keystone@'%' yang diidentifikasi oleh 'password';
Kueri OK, 0 baris terpengaruh (0,00 detik)

MariaDB [(none)]> hak istimewa flush;
Kueri OK, 0 baris terpengaruh (0,00 detik)

MariaDB [(tidak ada)]> keluar
Selamat tinggal</pre>


## [2]	Instal Keystone.
<pre>root@dlp:~#apt -y instal keystone python3-openstackclient apache2 libapache2-mod-wsgi-py3 python3-oauth2client</pre>

## [3]	Konfigurasikan Batu Kunci.
