<template>
  <div>
    <b-button class="in-front" style="top:1rem;left:1rem;">Click</b-button>
    <Map></Map>
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
