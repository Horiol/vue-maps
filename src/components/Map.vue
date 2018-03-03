<template>
  <div id="myMap" class="map"></div>
</template>

<script>

export default {
  name: 'Map',
  data () {
    return {
      myMap: null,
      markers: []
    }
  },
  mounted () {
    this.myMap = window.L.map('myMap', {
      zoomControl: false
    }).setView([0, 0], 2)

    // add zoom control with your options
    window.L.control.zoom({
      position: 'bottomright'
    }).addTo(this.myMap)

    window.L.tileLayer('https://cartodb-basemaps-{s}.global.ssl.fastly.net/light_all/{z}/{x}/{y}.png', {
      maxZoom: 19
    }).addTo(this.myMap)
  },
  methods: {
    setCurrentLocation: function (position) {
      for (var i = 0; i < this.markers.length; i++) {
        this.myMap.removeLayer(this.markers[i])
      }
      this.merkers = []
      this.setLocation(position)
      this.setMarker(position)
    },
    setLocation: function (position) {
      this.myMap.setView([position.coords.latitude, position.coords.longitude], 18)
    },
    setMarker: function (position) {
      var marker = window.L.marker([position.coords.latitude, position.coords.longitude])
      this.markers.push(marker)
      marker.addTo(this.myMap)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.map{
  height:100vh;
}
</style>
