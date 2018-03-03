<template>
  <div id="myMap" class="map">
  </div>
</template>

<script>

export default {
  name: 'Map',
  data () {
    return {
      myMap: null
    }
  },
  mounted () {
    var L = window.L
    this.myMap = L.map('myMap', {
      zoomControl: false
    }).setView([0, 0], 2)

    // add zoom control with your options
    L.control.zoom({
      position: 'bottomright'
    }).addTo(this.myMap)

    L.tileLayer('https://cartodb-basemaps-{s}.global.ssl.fastly.net/light_all/{z}/{x}/{y}.png', {
      maxZoom: 19
    }).addTo(this.myMap)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.map{
  height:100vh;
}
</style>
