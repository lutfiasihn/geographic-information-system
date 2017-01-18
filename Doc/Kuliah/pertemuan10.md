**Latar Belakang**

Pada materi kali ini akan sedikit membahas tentang pengertian OpenLayers, apa yang dimaksud dengan markers dan bagaimana cara untuk menampilkan markers?

**Pembahasan**

OpenLayers adalah library Javascript murni untuk menampilkan data peta di berbagai web browser, tanpa server side dependencies. Open Layer adalah bersifat Free Software, yang dibangun oleh komunitas Open Source.

Markers base layer sangat mudah dipergunakan dan memungkinkan penggunaan fungsi addMarkers untuk menambah marker pada layer. Hanya mendukung point/ titik.

Cara untuk menampilkan marker dengan openlayer yaitu buka website ini [http://openlayers.org/en/latest/examples/overlay.html](http://openlayers.org/en/latest/examples/overlay.html) kemudian copy kan seluruh kodenya dan simpan dengan format html. Source code nya seperti dibawah ini:

&lt;!DOCTYPE html&gt;

&lt;html&gt;

  &lt;head&gt;

    &lt;title&gt;Overlay&lt;/title&gt;

    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://openlayers.org/en/v3.20.1/css/ol.css&quot; type=&quot;text/css&quot;&gt;

    &lt;!-- The line below is only needed for old environments like Internet Explorer and Android 4.x --&gt;

    &lt;script src=&quot;https://cdn.polyfill.io/v2/polyfill.min.js?features=requestAnimationFrame,Element.prototype.classList,URL&quot;&gt;&lt;/script&gt;

    &lt;script src=&quot;https://openlayers.org/en/v3.20.1/build/ol.js&quot;&gt;&lt;/script&gt;

    &lt;script src=&quot;https://code.jquery.com/jquery-2.2.3.min.js&quot;&gt;&lt;/script&gt;

    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css&quot;&gt;

    &lt;script src=&quot;https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js&quot;&gt;&lt;/script&gt;

    &lt;style&gt;

      #marker {

        width: 30px;

        height: 30px;

        border: 7px solid #088;

        border-radius: 60px;

        background-color: #0000CD;

        opacity: 3.0;

      }

      #bandung {

        text-decoration: none;

        color: #FF0000;

        font-size: 11pt;

        font-weight: bold;

      }

      #marker1 {

        width: 30px;

        height: 30px;

        border: 7px solid #088;

        border-radius: 60px;

        background-color: #0000CD;

        opacity: 3.0;

      }

    &lt;/style&gt;

  &lt;/head&gt;

  &lt;body&gt;

    &lt;div id=&quot;map&quot; class=&quot;map&quot;&gt;&lt;/div&gt;

    &lt;div style=&quot;display: none;&quot;&gt;

      &lt;!-- Clickable label for Vienna --&gt;

      &lt;a class=&quot;overlay&quot; id=&quot;bandung&quot; target=&quot;\_blank&quot; href=&quot;https://id.wikipedia.org/wiki/Kota\_Bandung&quot;&gt;Bandung&lt;/a&gt;

      &lt;div id=&quot;marker&quot; title=&quot;Marker&quot;&gt;&lt;/div&gt;

      &lt;!-- Popup --&gt;

      &lt;div id=&quot;popup&quot; title=&quot;Welcome to My Maps&quot;&gt;&lt;/div&gt;

    &lt;/div&gt;

    &lt;script&gt;

      var map = new ol.Map({

        layers: [

          new ol.layer.Tile({

            source: new ol.source.XYZ({

              url: &#39;https://map.vas.web.id/wmts/agm/webmercator/{z}/{x}/{y}.png&#39;

            })

          })

        ],

        target: &#39;map&#39;,

        view: new ol.View({

          center: ol.proj.transform([118.015776, -2.6000285], &#39;EPSG:4326&#39;, &#39;EPSG:3857&#39;),

          zoom: 5

        })

      });

      var pos = ol.proj.fromLonLat([107.609810,-6.914744]);

      // Vienna marker

      var marker = new ol.Overlay({

        position: pos,

        positioning: &#39;center-center&#39;,

        element: document.getElementById(&#39;marker&#39;),

        stopEvent: false

      });

      map.addOverlay(marker);

      // Vienna label

      var bandung = new ol.Overlay({

        position: pos,

        element: document.getElementById(&#39;bandung&#39;)

      });

      map.addOverlay(bandung);

      var pos1 = ol.proj.fromLonLat([113.4739,-7.1542]);

      // Vienna marker

      var marker1 = new ol.Overlay({

        position: pos1,

        positioning: &#39;center-center&#39;,

        element: document.getElementById(&#39;marker1&#39;),

        stopEvent: false

      });

      map.addOverlay(marker1);

      // Popup showing the position the user clicked

      var popup = new ol.Overlay({

        element: document.getElementById(&#39;popup&#39;)

      });

      map.addOverlay(popup);

      map.on(&#39;click&#39;, function(evt) {

        var element = popup.getElement();

        var coordinate = evt.coordinate;

        var hdms = ol.coordinate.toStringHDMS(ol.proj.transform(

            coordinate, &#39;EPSG:3857&#39;, &#39;EPSG:4326&#39;));

        $(element).popover(&#39;destroy&#39;);

        popup.setPosition(coordinate);

        // the keys are quoted to prevent renaming in ADVANCED mode.

        $(element).popover({

          &#39;placement&#39;: &#39;top&#39;,

          &#39;animation&#39;: false,

          &#39;html&#39;: true,

          &#39;content&#39;: &#39;&lt;p&gt;The location you clicked was:&lt;/p&gt;&lt;code&gt;&#39; + hdms + &#39;&lt;/code&gt;&#39;

        });

        $(element).popover(&#39;show&#39;);

      });

    &lt;/script&gt;

  &lt;/body&gt;

&lt;/html&gt;

Output dari source code diatas yaitu :

<p align ="center">
<img src="../../img/openlayer.JPG" width="600px">
</p>

**Kesimpulan**

Perlu dilakukan praktek secara langsung agar mengetahui lebih detail tentang OpenLayers, Markers dan Cara membuatnya.