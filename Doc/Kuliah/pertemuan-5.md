Create Shape File

Membuat data geometri sendiri. Langkah-langkah:

1. Gunakan import pyshp &quot;import shapefile&quot;
2. Instansiasi method writer a = shapefile writer()

Shape file dibagi menjadi 2 yaitu:

1. File shp/geometri. Yang bisa dipakai dibagi menjadi 3 jenis yaitu point, polyline dan polygon.
2. Dbf (table identitas geometri)

Contoh point:

Menambahkan record ke 1

a.point(x,y) ? dimana x dan y adalah koordinat (longitude dan latitude) atau

a.point (x,y,0,0)

contoh polyline:

a.poly (shapetype=3, parts [[[x,y,z,w, [x2,y2,z2,w2]]]]

a.poly (shapetype=5, parts [[[ ]],[   ]]]]

1. Dbf yaitu field untuk menemukan atribut table.

Contohnya: a.field(&#39;kota&#39;,&#39;c&#39;,&#39;40&#39;) artinya yaitu ada field kota dengan type char sebanyak 40.

1. Isinya pada method record.

a.record (&#39;Bandung&#39;)