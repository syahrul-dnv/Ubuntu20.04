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

##	Tambahkan Pengguna dan Database di MariaDB untuk Keystone.
