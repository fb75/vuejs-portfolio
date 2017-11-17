<template>  
  <gmap-map
    :center="center"
    :zoom="10"
    style="width: auto; height: 250px;"
  >
    <gmap-marker
      :position="markers[0].position"
      :clickable="false"
      :draggable="true"       
    ></gmap-marker>
  </gmap-map>
</template>
 
<script>

 
  export default {
    data () {
      return {
        center: {lat: 43.1265396, lng: 12.3743287},
        markers: [{
          position: {lat: 43.1265396, lng: 12.3743287}
        }]
      }
    }
  }
</script> 