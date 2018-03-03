<template>
  <div>
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
