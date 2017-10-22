<!-- .slide: data-background="img/bg-main.png" -->

## 3D with [#esrijs](https://developers.arcgis.com/javascript/)
###  EU DevSummit 2017 - Speedgeeking

<br>

<small>
Javier Gutierrez | [javier_gutierrez@esri.com](mailto:javier_gutierrez@esri.com) | [@jgutierrez0](https://twitter.com/jgutierrez0)
<br>
ESRI R&amp;D Center Zürich
</small>

---

## let's go hiking?

---


<img src="./img/flat-hike.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none;" />

---

## not bad, but a bit 2D-ish..

---

## how about some mountains?

---

<img src="./img/hike3.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none; display:inline-block" />
<img src="./img/hike2.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none;display:inline-block" />

---

<img src="./img/hike1.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none; display:inline-block" />
<img src="./img/hike4.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none;display:inline-block" />


---

<img src="./img/hut1.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none; display:inline-block" />
<img src="./img/hut2.jpg" style="max-height: 600px; border:0; background: none; box-shadow: none;display:inline-block" />

https://www.silvrettahuette.ch

---

### Hike to Silvretta hut, in the Swiss Alps


<div class="twos">
  <div class="snippet">
    <pre>
      <code class="lang-js hljs javascript">
var map = new WebMap({
  portalItem:{
    id: "d721eb35a09747e4a1aa8bcd491d9ecc"
  }
});

var view = new MapView({
  map: map,
  container: "viewDiv"
});
      </code>
   </pre>
  </div>

  <div class="snippet-preview">
    <iframe id="frame-auto-cast" data-src="./snippets/hike-map.html"></iframe>
  </div>
</div>

---

### Hike to Silvretta hut, in the Swiss Alps, with a Legend!


<div class="twos">
  <div class="snippet">
    <pre>
      <code class="lang-js hljs javascript">
var map = new WebMap({
  portalItem:{
    id: "d721eb35a09747e4a1aa8bcd491d9ecc"
  }
});

var view = new MapView({
  map: map,
  container: "viewDiv"
});

var legend = new Legend({ view: view });
view.ui.add(legend);
      </code>
   </pre>
  </div>

  <div class="snippet-preview">
    <iframe id="frame-auto-cast" data-src="./snippets/hike-map-legend.html"></iframe>
  </div>
</div>


---

### Hike to Silvretta hut, in the Swiss Alps, with a Legend, in 3D! :)


<div class="twos">
  <div class="snippet">
    <pre>
      <code class="lang-js hljs javascript">
var map = new WebScene({
  portalItem:{
    id: "5682cd69fe5c451d8924d38d6cc918d4"
  }
});

var view = new SceneView({
  map: map,
  container: "viewDiv"
});

var legend = new Legend({ view: view });
view.ui.add(legend);
      </code>
   </pre>
  </div>

  <div class="snippet-preview">
    <iframe id="frame-auto-cast" data-src="./snippets/hike-scene.html"></iframe>
  </div>
</div>


---

### Hike to Silvretta hut, in the Swiss Alps, with a Legend, in 3D, <br> with Elevation! \o/


<div class="twos">
  <div class="snippet">
    <pre>
      <code class="lang-js hljs javascript">
var map = new WebScene({
  portalItem:{
    id: "5682cd69fe5c451d8924d38d6cc918d4"
  }
});

var view = new SceneView({
  map: map,
  container: "viewDiv"
});

var legend = new Legend({ view: view });
view.ui.add(legend);

view.then(() => {
  map.ground = "world-elevation";
});
      </code>
   </pre>
  </div>

  <div class="snippet-preview">
    <iframe id="frame-auto-cast" data-src="./snippets/hike-scene-elevation.html"></iframe>
  </div>
</div>

---

### More 3D: Set Camera


<div class="twos">
  <div class="snippet">
    <pre>
      <code class="lang-js hljs javascript">
view.then(() => {
  map.ground = "world-elevation";

  // use goTo for moving camera
  view.goTo({

    // console: JSON.stringify(view.camera.toJSON())
    tilt: 60,
    heading: 78,
    position: {
      x: 1108833,
      y: 5917218,
      z: 5432,
      spatialReference: { wkid: 3857 }
    }
  });
});
      </code>
   </pre>
  </div>

  <div class="snippet-preview">
    <iframe id="frame-auto-cast" data-src="./snippets/hike-scene-camera.html"></iframe>
  </div>
</div>

---


### More 3D: Callouts for Points


<div class="twos">
  <div class="snippet">
    <pre>
      <code class="lang-js hljs javascript">
view.then(() => {
map.layers.get
});
      </code>
   </pre>
  </div>

  <div class="snippet-preview">
    <iframe id="frame-auto-cast" data-src="./snippets/hike-scene-callouts.html"></iframe>
  </div>
</div>

