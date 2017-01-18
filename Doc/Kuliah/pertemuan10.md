**Latar Belakang**

Pada materi kali ini akan sedikit membahas tentang pengertian OpenLayers, apa yang dimaksud dengan markers dan bagaimana cara untuk menampilkan markers?

**Pembahasan**

OpenLayers adalah library Javascript murni untuk menampilkan data peta di berbagai web browser, tanpa server side dependencies. Open Layer adalah bersifat Free Software, yang dibangun oleh komunitas Open Source.

Markers base layer sangat mudah dipergunakan dan memungkinkan penggunaan fungsi addMarkers untuk menambah marker pada layer. Hanya mendukung point/ titik.

Cara untuk menampilkan marker dengan openlayer yaitu buka website ini [http://openlayers.org/en/latest/examples/overlay.html](http://openlayers.org/en/latest/examples/overlay.html) kemudian copy kan seluruh kodenya dan simpan dengan format html. Source code nya seperti dibawah ini:

<!DOCTYPE html>
<html>
  <head>
    <title>Overlay</title>
    <link rel="stylesheet" href="https://openlayers.org/en/v3.20.1/css/ol.css" type="text/css">
    <!-- The line below is only needed for old environments like Internet Explorer and Android 4.x -->
    <script src="https://cdn.polyfill.io/v2/polyfill.min.js?features=requestAnimationFrame,Element.prototype.classList,URL"></script>
    <script src="https://openlayers.org/en/v3.20.1/build/ol.js"></script>
    <script src="https://code.jquery.com/jquery-2.2.3.min.js"></script>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
    <style>
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
     
    </style>
  </head>
  <body>
    <div id="map" class="map"></div>
    <div style="display: none;">
      <!-- Clickable label for Vienna -->
      <a class="overlay" id="bandung" target="_blank" href="https://id.wikipedia.org/wiki/Kota_Bandung">Bandung</a>
      <div id="marker" title="Marker"></div>
      <!-- Popup -->
      <div id="popup" title="Welcome to My Maps"></div>
    </div>
    <script>

      var map = new ol.Map({
        layers: [
          new ol.layer.Tile({
            source: new ol.source.XYZ({
              url: 'https://map.vas.web.id/wmts/agm/webmercator/{z}/{x}/{y}.png'
            })
          })
        ],
        target: 'map',
        view: new ol.View({
          center: ol.proj.transform([118.015776, -2.6000285], 'EPSG:4326', 'EPSG:3857'),
          zoom: 5
        })
      });

      var pos = ol.proj.fromLonLat([107.609810,-6.914744]);

      // Vienna marker
      var marker = new ol.Overlay({
        position: pos,
        positioning: 'center-center',
        element: document.getElementById('marker'),
        stopEvent: false
      });
      map.addOverlay(marker);

      // Vienna label
      var bandung = new ol.Overlay({
        position: pos,
        element: document.getElementById('bandung')
      });
      map.addOverlay(bandung);

      var pos1 = ol.proj.fromLonLat([113.4739,-7.1542]);

      // Vienna marker
      var marker1 = new ol.Overlay({
        position: pos1,
        positioning: 'center-center',
        element: document.getElementById('marker1'),
        stopEvent: false
      });
      map.addOverlay(marker1);

      // Popup showing the position the user clicked
      var popup = new ol.Overlay({
        element: document.getElementById('popup')
      });
      map.addOverlay(popup);

      map.on('click', function(evt) {
        var element = popup.getElement();
        var coordinate = evt.coordinate;
        var hdms = ol.coordinate.toStringHDMS(ol.proj.transform(
            coordinate, 'EPSG:3857', 'EPSG:4326'));

        $(element).popover('destroy');
        popup.setPosition(coordinate);
        // the keys are quoted to prevent renaming in ADVANCED mode.
        $(element).popover({
          'placement': 'top',
          'animation': false,
          'html': true,
          'content': '<p>The location you clicked was:</p><code>' + hdms + '</code>'
        });
        $(element).popover('show');
      });
    </script>
  </body>
</html>


Output dari source code diatas yaitu :

<p align ="center">
<img src="../../img/openlayer.JPG" width="600px">
</p>

**Kesimpulan**

Perlu dilakukan praktek secara langsung agar mengetahui lebih detail tentang OpenLayers, Markers dan Cara membuatnya.