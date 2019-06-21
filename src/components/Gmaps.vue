<template>
  <div id="map">

  </div>
</template>

<script>
// Importamos la configuración de google Maps
import gmapsInit from '@/utils/gmaps'

export default {
  name: "Gmaps",
  data: () => ({

  }),
  async mounted(){
    try {
      // Cargamos las dependencias
      const google = await gmapsInit()
      // Inicializamos google maps
      const map = new google.maps.Map(document.getElementById('map'),{
        center: {lat: -34.397, lng: 150.644},
        zoom: 8
      })

      /*
      // const geocoder = new google.maps.Geocoder()
      geocoder.geocode({ address: 'Austria'}, (results, status) => {
        if(status !== 'OK' || !results[0]) {
          throw new Error(status)
        }

        map.setCenter(results[0].geometry.location)
        map.fitBounds(results[0].geometry.viewport)
      })
      */
    } catch (e) {
      console.error(e)
    }
  }
}
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}

#map {
  width: 100%;
  height: 400px;
}
</style>
