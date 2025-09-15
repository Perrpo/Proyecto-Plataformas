<template>
  <div id="map-view">
    <h2>Puntos de Recolección</h2>
    <div ref="map" class="map-container"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from 'vue';

export default defineComponent({
  name: 'MapView',
  setup() {
    const initMap = () => {
      const map = new google.maps.Map(document.getElementById('map') as HTMLElement, {
        center: { lat: -34.397, lng: 150.644 },
        zoom: 8,
      });

      // Aquí puedes agregar marcadores para los puntos de recolección
      const locations = [
        { lat: -34.397, lng: 150.644, name: 'ONG 1' },
        { lat: -34.407, lng: 150.654, name: 'ONG 2' },
      ];

      locations.forEach(location => {
        new google.maps.Marker({
          position: { lat: location.lat, lng: location.lng },
          map: map,
          title: location.name,
        });
      });
    };

    onMounted(() => {
      initMap();
    });

    return {};
  },
});
</script>

<style scoped>
.map-container {
  height: 400px;
  width: 100%;
}
</style>