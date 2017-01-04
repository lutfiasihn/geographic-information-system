**Latar belakang**

Ada dua file konfigurasi yang digunakan oleh MapProxy, yaitu mapproxy.yaml dan seed.yaml.dalam tulisan ini hanya akan sedikit membahas sedikit tentang mapproxyyaml

**Pembahasan**

Mapproxy.yaml yaitu konfigurasi utama map proxy. Ini mengkonfigurasikan semua aspek server, contohnya seperti server mana yang harus dimulai, dimana server tersebut berasal, apa yang harus di cache, dan lain-lain. Konfigurasi ini menggunakan format yaml. Konfigurasi mapproxy dikelompokkan menjadi beberapa bagian. Masing-masing bagian menkonfigurasi aspek yang berbeda dari mapproxy. Bagian-bagian tersebut yaitu:

_Globals :_ internal dari mapproxy dan nilai default yang digunaka dalam bagian konfigurasi lainnya.

_Services :_ Layanan MapProxy penawaran, misalnya WMS atau TMS.

_Sources :_ Menentukan MapProxy mana yang dapat mengambil data baru.

_Caches :_ Konfigurasi cache internal.

_Layers :_  Konfigurasi lapisan MapProxy, Setiap lapisan dapat terdiri dari beberapa sources dan caches.

_Grids_ : Tentukan grid yang menggunakan MapProxy untuk menyelaraskan gambar cache.

Bagaimana urutannya itu tidak penting, sehingga Anda dapat mengatur dengan cara Anda.

Ada beberapa bagian opsional lain:

bagian: YAML mendukung referensi dengan itu Anda dapat menentukan bagian konfigurasi dan menggunakannya dalam seksi konfigurasi lainnya. Misalnya, Anda dapat menentukan semua yang Anda coverage di satu tempat dan referensi mereka dari sources. Namun, MapProxy akan log peringatan jika Anda menempatkan rujukan di tempat di mana itu bukan pilihan yang valid. Untuk mencegah peringatan ini, Anda disarankan untuk menempatkan potongan konfigurasi ini di dalam setiap bagian.

Sebagai contoh:

parts:

  coverages:

      mycoverage: &amp;mycoverage

        bbox: [0, 0, 10, 10]

        srs: &#39;EPSG:4326&#39;

sources:

  mysource1:

    coverage: \*mycoverage

    ...

  mysource2:

    coverage: \*mycoverage

    ...

**base**

Anda dapat membagi konfigurasi menjadi beberapa file dengan opsi dasar. Opsi dasar load file lain dan menggabungkan kamus konfigurasi dimuat bersama-sama - itu bukan literal termasuk dari file lainnya. Sebagai contoh:

base: [mygrids.yaml, mycaches\_sources.yaml]

service: ...

layers: ...

## **services**

Di sini Anda dapat mengkonfigurasi layanan harus dimulai. Konfigurasi untuk semua layanan yang dijelaskan dalam dokumentasi Layanan. Berikut adalah contoh:

services:

  tms:

  wms:

    md:

      title: MapProxy Example WMS

      contact:

      # [...]

**Saran**

Diperlukan banyak belajar dengan membaca atau praktek langsung agar dapat memahami lebih jauh tentang map proxy.