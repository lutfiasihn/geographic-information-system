Latar Belakang

        MapServer merupakan aplikasi yang menggunakan pendekatan open source yang dikembangkan oleh Team pengembang software di Universitas Minnesota dengan tujuan agar aplikasi tersebut dapat diperoleh secara gratis, bebas dipergunakan , dimodifikasi dan di distribusikan.

Pembahasan

        Seorang programmer dapat melakukan modifikasi pada peta dengan menggunakan MapScript. MapScript yaitu API (Application Programming Interface) yang disediakan oleh MapServer.

        Mapproxy berfungsi untuk melakukan caching agar semua request tidak langsung diteruskan kepada mapserver. Hal ini dilakukan karena pentingnya menjaga performansi aplikasi agar load peta tidak terlalu lama.

Cara instalasi :

1. Jalankan di virtual box, iso centos dan virtual box ada di halaman download setelah itu pastikan koneksi jaringan virtual box bisa diakses dari komputer host

2. Dicentos buka terinal login sebagai root

# gvm  install npm sever selesai

Map proxy  untuk menampung hasil gambar dari map server agar konsumsi komputer bisa direduksi.

Cara instalasi :

1. install python -pip dan python-dev
# gvm install python-pip python-dev

2. install vwsqi
# pip-install uvwsqi

Penutup

MapServer merupakan aplikasi freeware dan open source yang memungkinkan kita menampilkan data spasial (peta) di web.sedangkan map proxy menampung hasil gambar dari map server agar komputer bisa direduksi.

Saran

Perlu dilakukan praktek yang lebih intens agar dapat memperdalam pembelajaran.