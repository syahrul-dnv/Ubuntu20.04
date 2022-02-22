# OpenStack Xena : Konfigurasikan Keystone #2

Tambahkan Proyek di Keystone.
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

## [1]	Muat variabel lingkungan terlebih dahulu.
Nilai untuk [OS_PASSWORD] berasal dari kata sandi saat mengonfigurasi keystone bootstrap .
Untuk [OS_AUTH_URL], tentukan nama host atau alamat IP server Keystone.
