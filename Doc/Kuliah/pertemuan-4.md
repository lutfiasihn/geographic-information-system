1. LATAR BELAKANG

Data Geospasial merupakan data tentang geografis, ukuran, dimensi dan karakteristik objek alam dan buatan manusia yang berada dibawah atau diatas permukaan bumi.data geospasial yang usdah diperoleh ini dapat digunakan sebagai alat bantu dalam pengambilan keputusan atau pelaksanaan kegiatan yang berhubungan dengan ruang bumi.

1. PEMBAHASAN

Retrieve Data Geospasial yaitu untuk mengambil data geometri dan database data geospasial retrieve berfungsi untuk mengambil salah satu data vector.

Metode retrieve ada 2 yaitu:

1. Shp (data geometri)

        Shape (n)

        Shapes ()

1. Dbf (table)

        Record(n)

        Records()

        Fields

Operasi pemrograman pengambilan data geospasial :

1. Menggunakan library pyshp
2. Panggil library di python menggunakan (import shape file)
3. Instalasi kelas dengan constrack input file

Contohnya:

Sf = shapefile.Reader (&#39;file.shp&#39;)

Keterangan:

Sf merupakan variable

Shapefile merupakan class shapefile

Reader merupakan method dari class shape file

File.shp merupakan parameter

Contoh :

Import shapefile

Sf = Shapefile.Reader (&#39;bts\_negara.shp&#39;)

#apa saja field di dbf

Sf.fields

#ambil semua di dbf

Sf.records()

#ambil salah satu record ke 1

Sf.record(0)

#ambil data geometri semua

Sf.shapes()

#ambil data geometri ke 1

Sf.shape(0)

#masukan data geometri ke 0 ke variable

a = sf.shape(0)

dir (a) ? bbox, shapetype, points, ports

Data shp

bbox = bounding box (titik pinggiran peta).

Shape type

Point = 1

Polyline = 3 (titik tidak bertemu )

Polygon = 5 (titik bertemu dari ititik awal)

1. KESIMPULAN

Retrieve data merupakan untuk mengambil data dari suatu data vector.

Saran:

Untuk melakukan retrieve data maka harus ditentukan dahulu data apa yang akan di retrieve dalam peta.