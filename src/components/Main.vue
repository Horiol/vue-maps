<template>
  <div>
    <b-button class="in-front" style="top:1rem;left:1rem;" title="Current location" @click="setLocation">
      <i class="fa fa-compass fa-2x"></i>
    </b-button>
    <Map ref="myMap"></Map>
  </div>
</template>

<script>
import Map from './Map'

export default {
  name: 'Main',
  components: {
    Map
  },
  data () {
    return {
    }
  },
  methods: {
    setLocation: function () {
      navigator.geolocation.getCurrentPosition(this.$refs.myMap.setCurrentLocation)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .in-front{
    position: absolute;
    z-index:9999;
  }

</style>
