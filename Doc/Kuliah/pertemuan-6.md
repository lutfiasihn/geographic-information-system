Create point

**Latar Belakang**

        Sebuah titik dapat menggambarkan objek geografi yang berbeda-beda menurut skalanya. Jika pada peta berskala kecil, titik dapat digunakan untuk menggambar kota namun pada peta yang berskala besar, titik digunakan untuk menggambarkan wilayah yang lebih spesifik dalam kota.

**Pembahasan**

**Write Point**

w = shapeType
w.field (&#39;Provinsi&#39;,&#39;C&#39;,&#39;40&#39;)
w.field (&#39;Jawa Barat&#39;,&#39;Nita&#39;)
w.record (&#39;Jawa Barat&#39;,&#39;Nita&#39;)
w.point (10,10,0,0)
w.save(&#39;provinsi.shp&#39;)
exit()

**Read Point**

sf = shape

sf.records()

sf.record(0)

sf.record(1)

sf.shapes()[0].point

**Kesimpulan**

Titik (point) menggambarkan objek yang berbeda-beda menurut skala.

**Saran **

Dibutuhkan ketelitian dalam menentukan titik objek dalam suatu peta.