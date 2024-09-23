```python
import pandas as pd 
import numpy as np 
import folium 
import os


# Load data
file_path = os.path.join("data", "Interview_Programmers_OptiSolio.xlsx")
df = pd.read_excel(file_path, sheet_name='Sheet1')
coordinates = df.iloc[:-2, [1, 2]].values #Coordinates stored in a Numpy array
depot= [35.324662, 25.133215]
demands1= df.iloc[:-2,3].values #Loads of day 31/08
demands2= df.iloc[:-2,4].values #Loads of day 07/09


# Create a map centered around the depot
m = folium.Map(location=depot, tiles='OpenStreetMap', zoom_start=14)
for coord in coordinates:
    folium.Marker(location=coord).add_to(m)

folium.Marker(location=depot, icon=folium.Icon(color="red")).add_to(m)

m


```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe srcdoc="&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;

    &lt;meta http-equiv=&quot;content-type&quot; content=&quot;text/html; charset=UTF-8&quot; /&gt;

        &lt;script&gt;
            L_NO_TOUCH = false;
            L_DISABLE_3D = false;
        &lt;/script&gt;

    &lt;style&gt;html, body {width: 100%;height: 100%;margin: 0;padding: 0;}&lt;/style&gt;
    &lt;style&gt;#map {position:absolute;top:0;bottom:0;right:0;left:0;}&lt;/style&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://code.jquery.com/jquery-3.7.1.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js&quot;&gt;&lt;/script&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap-glyphicons.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.2.0/css/all.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css&quot;/&gt;

            &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width,
                initial-scale=1.0, maximum-scale=1.0, user-scalable=no&quot; /&gt;
            &lt;style&gt;
                #map_4e305cb879b56f1c353be1fb1860bd8f {
                    position: relative;
                    width: 100.0%;
                    height: 100.0%;
                    left: 0.0%;
                    top: 0.0%;
                }
                .leaflet-container { font-size: 1rem; }
            &lt;/style&gt;

&lt;/head&gt;
&lt;body&gt;


            &lt;div class=&quot;folium-map&quot; id=&quot;map_4e305cb879b56f1c353be1fb1860bd8f&quot; &gt;&lt;/div&gt;

&lt;/body&gt;
&lt;script&gt;


            var map_4e305cb879b56f1c353be1fb1860bd8f = L.map(
                &quot;map_4e305cb879b56f1c353be1fb1860bd8f&quot;,
                {
                    center: [35.324662, 25.133215],
                    crs: L.CRS.EPSG3857,
                    zoom: 14,
                    zoomControl: true,
                    preferCanvas: false,
                }
            );





            var tile_layer_afabf40273e72357fd3b4d2122d333a9 = L.tileLayer(
                &quot;https://tile.openstreetmap.org/{z}/{x}/{y}.png&quot;,
                {&quot;attribution&quot;: &quot;\u0026copy; \u003ca href=\&quot;https://www.openstreetmap.org/copyright\&quot;\u003eOpenStreetMap\u003c/a\u003e contributors&quot;, &quot;detectRetina&quot;: false, &quot;maxNativeZoom&quot;: 19, &quot;maxZoom&quot;: 19, &quot;minZoom&quot;: 0, &quot;noWrap&quot;: false, &quot;opacity&quot;: 1, &quot;subdomains&quot;: &quot;abc&quot;, &quot;tms&quot;: false}
            );


            tile_layer_afabf40273e72357fd3b4d2122d333a9.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_eebf30a46d9f8385e4e473cdf6a94e6c = L.marker(
                [35.326936, 25.130738],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_0e272ae9381fefc1bf157b340d09076e = L.marker(
                [35.324765, 25.131832],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_3d45913276d92e5678fbd71001911b8b = L.marker(
                [35.325815, 25.125567],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_d0f4e5240e2654dbe218348bb1038e78 = L.marker(
                [35.324362, 25.13857],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_74b207ec9991d85278143b8f178882ca = L.marker(
                [35.323907, 25.12237],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_9e1fbb146ca446020c2336715c6324a3 = L.marker(
                [35.321053, 25.137196],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_af62bbef906ca78424f713cc5ab7d35c = L.marker(
                [35.322471, 25.124944],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_edc2b9a45c72b3c7f8b25a29ce6f23f1 = L.marker(
                [35.32613, 25.141145],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_f7ec0e2e7eabe9eb1b641c27e817d730 = L.marker(
                [35.327829, 25.13048],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_e0088998764d5714a1958c04be381b8e = L.marker(
                [35.327006, 25.124558],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_c6a622ba4783ea32dbf3e31d96bd2b5c = L.marker(
                [35.323785, 25.133399],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_7bda4a288ba5b29f71ceafb7d83f1150 = L.marker(
                [35.327794, 25.130545],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_ef4ffa8cbe683b94fb33f8f942e555ba = L.marker(
                [35.319478, 25.125438],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_b198814ccfb68f1fccfa9e8401293fdb = L.marker(
                [35.321596, 25.1237],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_caac55349309e7039d3d68a554979437 = L.marker(
                [35.322506, 25.14005],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_98bd8ef8c1ce28a2884ba82a3b89e55e = L.marker(
                [35.324662, 25.133215],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var icon_e9e0ec0765ac14e0d0a038d50b77aeb2 = L.AwesomeMarkers.icon(
                {&quot;extraClasses&quot;: &quot;fa-rotate-0&quot;, &quot;icon&quot;: &quot;info-sign&quot;, &quot;iconColor&quot;: &quot;white&quot;, &quot;markerColor&quot;: &quot;red&quot;, &quot;prefix&quot;: &quot;glyphicon&quot;}
            );
            marker_98bd8ef8c1ce28a2884ba82a3b89e55e.setIcon(icon_e9e0ec0765ac14e0d0a038d50b77aeb2);

&lt;/script&gt;
&lt;/html&gt;" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>




```python
import openrouteservice as ors
import folium
import pandas as pd


#DAY 31/08


# Initialize ORS Client
client = ors.Client(key='5b3ce3597851110001cf6248d35649aedb9e43ee9f045ce4e63f2b95')  
depot = [35.324662, 25.133215]  

#Vehicle Object
vehicles = [
    ors.optimization.Vehicle(
        id=1,
        start=list(reversed(depot)),  #Convert it to (Long, Lat)
        capacity=[50]                # Capacity of the vehicle
    )
]

#Summing up the data
deliveries_data = pd.DataFrame({
    'Lat': coordinates[:, 0],  
    'Lon': coordinates[:, 1],  
    'Loads1': demands1,        
    'Loads2': demands2         
})

#Jobs object for the API
deliveries = []
for delivery in deliveries_data.itertuples():
    deliveries.append(
        ors.optimization.Job(
            id=delivery.Index,
            location=[delivery.Lon, delivery.Lat],
            amount=[delivery.Loads1]
        )
    )

# Perform the optimization request
result = client.optimization(
    jobs=deliveries,
    vehicles=vehicles,
    geometry=True
)


# Extract the route from the result
route = result['routes'][0]

# Decode the polyline (route geometry) to get coordinates
decoded = ors.convert.decode_polyline(route['geometry'])

# Add the route to the existing map (m)
folium.GeoJson(
    name='Day 1 Route',
    data={"type": "FeatureCollection", "features": [{"type": "Feature",
                                                     "geometry": decoded,
                                                     "properties": {"color": "green"}
                                                     }]},
    style_function=lambda x: {"color": "green"}
).add_to(m)

m
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe srcdoc="&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;

    &lt;meta http-equiv=&quot;content-type&quot; content=&quot;text/html; charset=UTF-8&quot; /&gt;

        &lt;script&gt;
            L_NO_TOUCH = false;
            L_DISABLE_3D = false;
        &lt;/script&gt;

    &lt;style&gt;html, body {width: 100%;height: 100%;margin: 0;padding: 0;}&lt;/style&gt;
    &lt;style&gt;#map {position:absolute;top:0;bottom:0;right:0;left:0;}&lt;/style&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://code.jquery.com/jquery-3.7.1.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js&quot;&gt;&lt;/script&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap-glyphicons.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.2.0/css/all.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css&quot;/&gt;

            &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width,
                initial-scale=1.0, maximum-scale=1.0, user-scalable=no&quot; /&gt;
            &lt;style&gt;
                #map_4e305cb879b56f1c353be1fb1860bd8f {
                    position: relative;
                    width: 100.0%;
                    height: 100.0%;
                    left: 0.0%;
                    top: 0.0%;
                }
                .leaflet-container { font-size: 1rem; }
            &lt;/style&gt;

&lt;/head&gt;
&lt;body&gt;


            &lt;div class=&quot;folium-map&quot; id=&quot;map_4e305cb879b56f1c353be1fb1860bd8f&quot; &gt;&lt;/div&gt;

&lt;/body&gt;
&lt;script&gt;


            var map_4e305cb879b56f1c353be1fb1860bd8f = L.map(
                &quot;map_4e305cb879b56f1c353be1fb1860bd8f&quot;,
                {
                    center: [35.324662, 25.133215],
                    crs: L.CRS.EPSG3857,
                    zoom: 14,
                    zoomControl: true,
                    preferCanvas: false,
                }
            );





            var tile_layer_afabf40273e72357fd3b4d2122d333a9 = L.tileLayer(
                &quot;https://tile.openstreetmap.org/{z}/{x}/{y}.png&quot;,
                {&quot;attribution&quot;: &quot;\u0026copy; \u003ca href=\&quot;https://www.openstreetmap.org/copyright\&quot;\u003eOpenStreetMap\u003c/a\u003e contributors&quot;, &quot;detectRetina&quot;: false, &quot;maxNativeZoom&quot;: 19, &quot;maxZoom&quot;: 19, &quot;minZoom&quot;: 0, &quot;noWrap&quot;: false, &quot;opacity&quot;: 1, &quot;subdomains&quot;: &quot;abc&quot;, &quot;tms&quot;: false}
            );


            tile_layer_afabf40273e72357fd3b4d2122d333a9.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_eebf30a46d9f8385e4e473cdf6a94e6c = L.marker(
                [35.326936, 25.130738],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_0e272ae9381fefc1bf157b340d09076e = L.marker(
                [35.324765, 25.131832],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_3d45913276d92e5678fbd71001911b8b = L.marker(
                [35.325815, 25.125567],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_d0f4e5240e2654dbe218348bb1038e78 = L.marker(
                [35.324362, 25.13857],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_74b207ec9991d85278143b8f178882ca = L.marker(
                [35.323907, 25.12237],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_9e1fbb146ca446020c2336715c6324a3 = L.marker(
                [35.321053, 25.137196],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_af62bbef906ca78424f713cc5ab7d35c = L.marker(
                [35.322471, 25.124944],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_edc2b9a45c72b3c7f8b25a29ce6f23f1 = L.marker(
                [35.32613, 25.141145],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_f7ec0e2e7eabe9eb1b641c27e817d730 = L.marker(
                [35.327829, 25.13048],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_e0088998764d5714a1958c04be381b8e = L.marker(
                [35.327006, 25.124558],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_c6a622ba4783ea32dbf3e31d96bd2b5c = L.marker(
                [35.323785, 25.133399],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_7bda4a288ba5b29f71ceafb7d83f1150 = L.marker(
                [35.327794, 25.130545],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_ef4ffa8cbe683b94fb33f8f942e555ba = L.marker(
                [35.319478, 25.125438],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_b198814ccfb68f1fccfa9e8401293fdb = L.marker(
                [35.321596, 25.1237],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_caac55349309e7039d3d68a554979437 = L.marker(
                [35.322506, 25.14005],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_98bd8ef8c1ce28a2884ba82a3b89e55e = L.marker(
                [35.324662, 25.133215],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var icon_e9e0ec0765ac14e0d0a038d50b77aeb2 = L.AwesomeMarkers.icon(
                {&quot;extraClasses&quot;: &quot;fa-rotate-0&quot;, &quot;icon&quot;: &quot;info-sign&quot;, &quot;iconColor&quot;: &quot;white&quot;, &quot;markerColor&quot;: &quot;red&quot;, &quot;prefix&quot;: &quot;glyphicon&quot;}
            );
            marker_98bd8ef8c1ce28a2884ba82a3b89e55e.setIcon(icon_e9e0ec0765ac14e0d0a038d50b77aeb2);


            tile_layer_afabf40273e72357fd3b4d2122d333a9.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


        function geo_json_ca386361c69267bf7dd90a7401fbcd3c_styler(feature) {
            switch(feature.properties.color) {
                default:
                    return {&quot;color&quot;: &quot;green&quot;};
            }
        }

        function geo_json_ca386361c69267bf7dd90a7401fbcd3c_onEachFeature(feature, layer) {
            layer.on({
            });
        };
        var geo_json_ca386361c69267bf7dd90a7401fbcd3c = L.geoJson(null, {
                onEachFeature: geo_json_ca386361c69267bf7dd90a7401fbcd3c_onEachFeature,

                style: geo_json_ca386361c69267bf7dd90a7401fbcd3c_styler,
        });

        function geo_json_ca386361c69267bf7dd90a7401fbcd3c_add (data) {
            geo_json_ca386361c69267bf7dd90a7401fbcd3c
                .addData(data);
        }
            geo_json_ca386361c69267bf7dd90a7401fbcd3c_add({&quot;features&quot;: [{&quot;geometry&quot;: {&quot;coordinates&quot;: [[25.13321, 35.3247], [25.13251, 35.32468], [25.13214, 35.32469], [25.13183, 35.32472], [25.13131, 35.32476], [25.13135, 35.32469], [25.13147, 35.32422], [25.13217, 35.32424], [25.13225, 35.32377], [25.13228, 35.32361], [25.13218, 35.32358], [25.13216, 35.3233], [25.13334, 35.32335], [25.13337, 35.32378], [25.13337, 35.32379], [25.13339, 35.32397], [25.13344, 35.32427], [25.13354, 35.32472], [25.13355, 35.32528], [25.13356, 35.32563], [25.13365, 35.32648], [25.13387, 35.3272], [25.1339, 35.3273], [25.13393, 35.32738], [25.13334, 35.32717], [25.13258, 35.3269], [25.13235, 35.32684], [25.13213, 35.32684], [25.13188, 35.32686], [25.13182, 35.32686], [25.13109, 35.32693], [25.13074, 35.32696], [25.13057, 35.32698], [25.13064, 35.32739], [25.1307, 35.32779], [25.13055, 35.32781], [25.13048, 35.32781], [25.13021, 35.32784], [25.13014, 35.32744], [25.13007, 35.32703], [25.12955, 35.32708], [25.12907, 35.32714], [25.12847, 35.3272], [25.12777, 35.32729], [25.12769, 35.32732], [25.12761, 35.32738], [25.12754, 35.32735], [25.12712, 35.32719], [25.12638, 35.32694], [25.12625, 35.3269], [25.12544, 35.32658], [25.12438, 35.32612], [25.12417, 35.32606], [25.12364, 35.32601], [25.1236, 35.32614], [25.12323, 35.32669], [25.12362, 35.32683], [25.12392, 35.32692], [25.1244, 35.32697], [25.12456, 35.32699], [25.12592, 35.32712], [25.12628, 35.32713], [25.12603, 35.3277], [25.1258, 35.32826], [25.12613, 35.32831], [25.12669, 35.32842], [25.12712, 35.3279], [25.12754, 35.32735], [25.12712, 35.32719], [25.12638, 35.32694], [25.12625, 35.3269], [25.12544, 35.32658], [25.1255, 35.32649], [25.12552, 35.32644], [25.12554, 35.32581], [25.12554, 35.32578], [25.1255, 35.32566], [25.12509, 35.32479], [25.12504, 35.32468], [25.12486, 35.32433], [25.12508, 35.32428], [25.1251, 35.32411], [25.12509, 35.324], [25.12498, 35.32375], [25.12514, 35.32371], [25.12475, 35.32307], [25.12449, 35.32263], [25.12495, 35.32247], [25.12449, 35.32263], [25.124, 35.32282], [25.12371, 35.32292], [25.12363, 35.32294], [25.12305, 35.32313], [25.12289, 35.3232], [25.12269, 35.32333], [25.12229, 35.32363], [25.12226, 35.32369], [25.12226, 35.32376], [25.12229, 35.32386], [25.12234, 35.32392], [25.12235, 35.32394], [25.12249, 35.32402], [25.12276, 35.32408], [25.12253, 35.32421], [25.12148, 35.32471], [25.12147, 35.32474], [25.1214, 35.32522], [25.12119, 35.32522], [25.12125, 35.3246], [25.12134, 35.32401], [25.12144, 35.32383], [25.12161, 35.32362], [25.12087, 35.3233], [25.12143, 35.32251], [25.12171, 35.3222], [25.12211, 35.32183], [25.12247, 35.32161], [25.12285, 35.32142], [25.12334, 35.32183], [25.12371, 35.3216], [25.12334, 35.32183], [25.12285, 35.32142], [25.12367, 35.32109], [25.12448, 35.32071], [25.12413, 35.32022], [25.12468, 35.31998], [25.12499, 35.31981], [25.12546, 35.3195]], &quot;type&quot;: &quot;LineString&quot;}, &quot;properties&quot;: {&quot;color&quot;: &quot;green&quot;}, &quot;type&quot;: &quot;Feature&quot;}], &quot;type&quot;: &quot;FeatureCollection&quot;});



            geo_json_ca386361c69267bf7dd90a7401fbcd3c.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);

&lt;/script&gt;
&lt;/html&gt;" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>




```python
import openrouteservice as ors
import folium
import pandas as pd

#DAY 07/09



#Vehicle Object
vehicles = [
    ors.optimization.Vehicle(
        id=1,
        start=list(reversed(depot)),  #Convert it to (Long, Lat)
        capacity=[50]                # Capacity of the vehicle
    )
]

#Delivery Jobs for the API
deliveries2 = []
for delivery in deliveries_data.itertuples():
    deliveries2.append(
        ors.optimization.Job(
            id=delivery.Index,
            location=[delivery.Lon, delivery.Lat],
            amount=[delivery.Loads2]
        )
    )

# Perform the optimization request
result = client.optimization(
    jobs=deliveries2,
    vehicles=vehicles,
    geometry=True
)

# Add the route to the map 
route = result['routes'][0]
decoded = ors.convert.decode_polyline(route['geometry'])

# Add the decoded route to the map
folium.GeoJson(
    name='Day 2 Route',
    data={"type": "FeatureCollection", "features": [{"type": "Feature",
                                                     "geometry": decoded,
                                                     "properties": {"color": "green"}
                                                     }]},
    style_function=lambda x: {"color": "green"}
).add_to(m)

m

```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe srcdoc="&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;

    &lt;meta http-equiv=&quot;content-type&quot; content=&quot;text/html; charset=UTF-8&quot; /&gt;

        &lt;script&gt;
            L_NO_TOUCH = false;
            L_DISABLE_3D = false;
        &lt;/script&gt;

    &lt;style&gt;html, body {width: 100%;height: 100%;margin: 0;padding: 0;}&lt;/style&gt;
    &lt;style&gt;#map {position:absolute;top:0;bottom:0;right:0;left:0;}&lt;/style&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://code.jquery.com/jquery-3.7.1.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js&quot;&gt;&lt;/script&gt;
    &lt;script src=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js&quot;&gt;&lt;/script&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap-glyphicons.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.2.0/css/all.min.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css&quot;/&gt;
    &lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css&quot;/&gt;

            &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width,
                initial-scale=1.0, maximum-scale=1.0, user-scalable=no&quot; /&gt;
            &lt;style&gt;
                #map_4e305cb879b56f1c353be1fb1860bd8f {
                    position: relative;
                    width: 100.0%;
                    height: 100.0%;
                    left: 0.0%;
                    top: 0.0%;
                }
                .leaflet-container { font-size: 1rem; }
            &lt;/style&gt;

&lt;/head&gt;
&lt;body&gt;


            &lt;div class=&quot;folium-map&quot; id=&quot;map_4e305cb879b56f1c353be1fb1860bd8f&quot; &gt;&lt;/div&gt;

&lt;/body&gt;
&lt;script&gt;


            var map_4e305cb879b56f1c353be1fb1860bd8f = L.map(
                &quot;map_4e305cb879b56f1c353be1fb1860bd8f&quot;,
                {
                    center: [35.324662, 25.133215],
                    crs: L.CRS.EPSG3857,
                    zoom: 14,
                    zoomControl: true,
                    preferCanvas: false,
                }
            );





            var tile_layer_afabf40273e72357fd3b4d2122d333a9 = L.tileLayer(
                &quot;https://tile.openstreetmap.org/{z}/{x}/{y}.png&quot;,
                {&quot;attribution&quot;: &quot;\u0026copy; \u003ca href=\&quot;https://www.openstreetmap.org/copyright\&quot;\u003eOpenStreetMap\u003c/a\u003e contributors&quot;, &quot;detectRetina&quot;: false, &quot;maxNativeZoom&quot;: 19, &quot;maxZoom&quot;: 19, &quot;minZoom&quot;: 0, &quot;noWrap&quot;: false, &quot;opacity&quot;: 1, &quot;subdomains&quot;: &quot;abc&quot;, &quot;tms&quot;: false}
            );


            tile_layer_afabf40273e72357fd3b4d2122d333a9.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_eebf30a46d9f8385e4e473cdf6a94e6c = L.marker(
                [35.326936, 25.130738],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_0e272ae9381fefc1bf157b340d09076e = L.marker(
                [35.324765, 25.131832],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_3d45913276d92e5678fbd71001911b8b = L.marker(
                [35.325815, 25.125567],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_d0f4e5240e2654dbe218348bb1038e78 = L.marker(
                [35.324362, 25.13857],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_74b207ec9991d85278143b8f178882ca = L.marker(
                [35.323907, 25.12237],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_9e1fbb146ca446020c2336715c6324a3 = L.marker(
                [35.321053, 25.137196],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_af62bbef906ca78424f713cc5ab7d35c = L.marker(
                [35.322471, 25.124944],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_edc2b9a45c72b3c7f8b25a29ce6f23f1 = L.marker(
                [35.32613, 25.141145],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_f7ec0e2e7eabe9eb1b641c27e817d730 = L.marker(
                [35.327829, 25.13048],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_e0088998764d5714a1958c04be381b8e = L.marker(
                [35.327006, 25.124558],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_c6a622ba4783ea32dbf3e31d96bd2b5c = L.marker(
                [35.323785, 25.133399],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_7bda4a288ba5b29f71ceafb7d83f1150 = L.marker(
                [35.327794, 25.130545],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_ef4ffa8cbe683b94fb33f8f942e555ba = L.marker(
                [35.319478, 25.125438],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_b198814ccfb68f1fccfa9e8401293fdb = L.marker(
                [35.321596, 25.1237],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_caac55349309e7039d3d68a554979437 = L.marker(
                [35.322506, 25.14005],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var marker_98bd8ef8c1ce28a2884ba82a3b89e55e = L.marker(
                [35.324662, 25.133215],
                {}
            ).addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            var icon_e9e0ec0765ac14e0d0a038d50b77aeb2 = L.AwesomeMarkers.icon(
                {&quot;extraClasses&quot;: &quot;fa-rotate-0&quot;, &quot;icon&quot;: &quot;info-sign&quot;, &quot;iconColor&quot;: &quot;white&quot;, &quot;markerColor&quot;: &quot;red&quot;, &quot;prefix&quot;: &quot;glyphicon&quot;}
            );
            marker_98bd8ef8c1ce28a2884ba82a3b89e55e.setIcon(icon_e9e0ec0765ac14e0d0a038d50b77aeb2);


            tile_layer_afabf40273e72357fd3b4d2122d333a9.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


        function geo_json_ca386361c69267bf7dd90a7401fbcd3c_styler(feature) {
            switch(feature.properties.color) {
                default:
                    return {&quot;color&quot;: &quot;green&quot;};
            }
        }

        function geo_json_ca386361c69267bf7dd90a7401fbcd3c_onEachFeature(feature, layer) {
            layer.on({
            });
        };
        var geo_json_ca386361c69267bf7dd90a7401fbcd3c = L.geoJson(null, {
                onEachFeature: geo_json_ca386361c69267bf7dd90a7401fbcd3c_onEachFeature,

                style: geo_json_ca386361c69267bf7dd90a7401fbcd3c_styler,
        });

        function geo_json_ca386361c69267bf7dd90a7401fbcd3c_add (data) {
            geo_json_ca386361c69267bf7dd90a7401fbcd3c
                .addData(data);
        }
            geo_json_ca386361c69267bf7dd90a7401fbcd3c_add({&quot;features&quot;: [{&quot;geometry&quot;: {&quot;coordinates&quot;: [[25.13321, 35.3247], [25.13251, 35.32468], [25.13214, 35.32469], [25.13183, 35.32472], [25.13131, 35.32476], [25.13135, 35.32469], [25.13147, 35.32422], [25.13217, 35.32424], [25.13225, 35.32377], [25.13228, 35.32361], [25.13218, 35.32358], [25.13216, 35.3233], [25.13334, 35.32335], [25.13337, 35.32378], [25.13337, 35.32379], [25.13339, 35.32397], [25.13344, 35.32427], [25.13354, 35.32472], [25.13355, 35.32528], [25.13356, 35.32563], [25.13365, 35.32648], [25.13387, 35.3272], [25.1339, 35.3273], [25.13393, 35.32738], [25.13334, 35.32717], [25.13258, 35.3269], [25.13235, 35.32684], [25.13213, 35.32684], [25.13188, 35.32686], [25.13182, 35.32686], [25.13109, 35.32693], [25.13074, 35.32696], [25.13057, 35.32698], [25.13064, 35.32739], [25.1307, 35.32779], [25.13055, 35.32781], [25.13048, 35.32781], [25.13021, 35.32784], [25.13014, 35.32744], [25.13007, 35.32703], [25.12955, 35.32708], [25.12907, 35.32714], [25.12847, 35.3272], [25.12777, 35.32729], [25.12769, 35.32732], [25.12761, 35.32738], [25.12754, 35.32735], [25.12712, 35.32719], [25.12638, 35.32694], [25.12625, 35.3269], [25.12544, 35.32658], [25.12438, 35.32612], [25.12417, 35.32606], [25.12364, 35.32601], [25.1236, 35.32614], [25.12323, 35.32669], [25.12362, 35.32683], [25.12392, 35.32692], [25.1244, 35.32697], [25.12456, 35.32699], [25.12592, 35.32712], [25.12628, 35.32713], [25.12603, 35.3277], [25.1258, 35.32826], [25.12613, 35.32831], [25.12669, 35.32842], [25.12712, 35.3279], [25.12754, 35.32735], [25.12712, 35.32719], [25.12638, 35.32694], [25.12625, 35.3269], [25.12544, 35.32658], [25.1255, 35.32649], [25.12552, 35.32644], [25.12554, 35.32581], [25.12554, 35.32578], [25.1255, 35.32566], [25.12509, 35.32479], [25.12504, 35.32468], [25.12486, 35.32433], [25.12508, 35.32428], [25.1251, 35.32411], [25.12509, 35.324], [25.12498, 35.32375], [25.12514, 35.32371], [25.12475, 35.32307], [25.12449, 35.32263], [25.12495, 35.32247], [25.12449, 35.32263], [25.124, 35.32282], [25.12371, 35.32292], [25.12363, 35.32294], [25.12305, 35.32313], [25.12289, 35.3232], [25.12269, 35.32333], [25.12229, 35.32363], [25.12226, 35.32369], [25.12226, 35.32376], [25.12229, 35.32386], [25.12234, 35.32392], [25.12235, 35.32394], [25.12249, 35.32402], [25.12276, 35.32408], [25.12253, 35.32421], [25.12148, 35.32471], [25.12147, 35.32474], [25.1214, 35.32522], [25.12119, 35.32522], [25.12125, 35.3246], [25.12134, 35.32401], [25.12144, 35.32383], [25.12161, 35.32362], [25.12087, 35.3233], [25.12143, 35.32251], [25.12171, 35.3222], [25.12211, 35.32183], [25.12247, 35.32161], [25.12285, 35.32142], [25.12334, 35.32183], [25.12371, 35.3216], [25.12334, 35.32183], [25.12285, 35.32142], [25.12367, 35.32109], [25.12448, 35.32071], [25.12413, 35.32022], [25.12468, 35.31998], [25.12499, 35.31981], [25.12546, 35.3195]], &quot;type&quot;: &quot;LineString&quot;}, &quot;properties&quot;: {&quot;color&quot;: &quot;green&quot;}, &quot;type&quot;: &quot;Feature&quot;}], &quot;type&quot;: &quot;FeatureCollection&quot;});



            geo_json_ca386361c69267bf7dd90a7401fbcd3c.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            tile_layer_afabf40273e72357fd3b4d2122d333a9.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


            geo_json_ca386361c69267bf7dd90a7401fbcd3c.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);


        function geo_json_89c9f044ba49dc8f26dda566e08bc98c_styler(feature) {
            switch(feature.properties.color) {
                default:
                    return {&quot;color&quot;: &quot;green&quot;};
            }
        }

        function geo_json_89c9f044ba49dc8f26dda566e08bc98c_onEachFeature(feature, layer) {
            layer.on({
            });
        };
        var geo_json_89c9f044ba49dc8f26dda566e08bc98c = L.geoJson(null, {
                onEachFeature: geo_json_89c9f044ba49dc8f26dda566e08bc98c_onEachFeature,

                style: geo_json_89c9f044ba49dc8f26dda566e08bc98c_styler,
        });

        function geo_json_89c9f044ba49dc8f26dda566e08bc98c_add (data) {
            geo_json_89c9f044ba49dc8f26dda566e08bc98c
                .addData(data);
        }
            geo_json_89c9f044ba49dc8f26dda566e08bc98c_add({&quot;features&quot;: [{&quot;geometry&quot;: {&quot;coordinates&quot;: [[25.13321, 35.3247], [25.13251, 35.32468], [25.1325, 35.32476], [25.13253, 35.3248], [25.13307, 35.32513], [25.13317, 35.32519], [25.13336, 35.32526], [25.13355, 35.32528], [25.13356, 35.32563], [25.13365, 35.32648], [25.13387, 35.3272], [25.1339, 35.3273], [25.13417, 35.32739], [25.13491, 35.3276], [25.13534, 35.32771], [25.13581, 35.32784], [25.13598, 35.32788], [25.13599, 35.32785], [25.13601, 35.32784], [25.13654, 35.32798], [25.13764, 35.32828], [25.13784, 35.32831], [25.13788, 35.32828], [25.13792, 35.32797], [25.1381, 35.32727], [25.13815, 35.32709], [25.13831, 35.32663], [25.13837, 35.32644], [25.13852, 35.3261], [25.13872, 35.32574], [25.13883, 35.32544], [25.13891, 35.32491], [25.13899, 35.32456], [25.13904, 35.32439], [25.13924, 35.32357], [25.13937, 35.32311], [25.13947, 35.32273], [25.13957, 35.32243], [25.14005, 35.32244], [25.13957, 35.32243], [25.13971, 35.32202], [25.13977, 35.32182], [25.13964, 35.32177], [25.13939, 35.32167], [25.13914, 35.32159], [25.13893, 35.32155], [25.13863, 35.32154], [25.13769, 35.32165], [25.13716, 35.32174], [25.13717, 35.32105], [25.13716, 35.32174], [25.13695, 35.32178], [25.13653, 35.32186], [25.13642, 35.32189], [25.13564, 35.32203], [25.13534, 35.32205], [25.13508, 35.32207], [25.13482, 35.32209], [25.1348, 35.32209], [25.13447, 35.3221], [25.134, 35.32213], [25.13363, 35.32215], [25.13324, 35.32215], [25.13334, 35.32335], [25.13337, 35.32378], [25.13337, 35.32379], [25.13339, 35.32397], [25.13344, 35.32427], [25.13354, 35.32472], [25.13355, 35.32528], [25.13356, 35.32563], [25.13365, 35.32648], [25.13387, 35.3272], [25.1339, 35.3273], [25.13393, 35.32738], [25.13334, 35.32717], [25.13258, 35.3269], [25.13235, 35.32684], [25.13213, 35.32684], [25.13188, 35.32686], [25.13182, 35.32686], [25.13109, 35.32693], [25.13074, 35.32696], [25.13057, 35.32698], [25.13064, 35.32739], [25.1307, 35.32779], [25.13055, 35.32781], [25.13048, 35.32781], [25.13021, 35.32784], [25.13014, 35.32744], [25.13007, 35.32703], [25.12955, 35.32708], [25.12907, 35.32714], [25.12847, 35.3272], [25.12777, 35.32729], [25.12769, 35.32732], [25.12761, 35.32738], [25.12754, 35.32735], [25.12712, 35.32719], [25.12638, 35.32694], [25.12625, 35.3269], [25.12544, 35.32658], [25.1255, 35.32649], [25.12552, 35.32644], [25.12554, 35.32581], [25.12554, 35.32578], [25.12487, 35.32595], [25.12446, 35.32607], [25.12438, 35.32612], [25.12417, 35.32606], [25.12364, 35.32601], [25.1236, 35.32614], [25.12323, 35.32669], [25.12362, 35.32683], [25.12392, 35.32692], [25.1244, 35.32697], [25.12456, 35.32699]], &quot;type&quot;: &quot;LineString&quot;}, &quot;properties&quot;: {&quot;color&quot;: &quot;green&quot;}, &quot;type&quot;: &quot;Feature&quot;}], &quot;type&quot;: &quot;FeatureCollection&quot;});



            geo_json_89c9f044ba49dc8f26dda566e08bc98c.addTo(map_4e305cb879b56f1c353be1fb1860bd8f);

&lt;/script&gt;
&lt;/html&gt;" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>




