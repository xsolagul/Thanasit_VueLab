<!-- <template>
  <div id="container">
    <manufacturer v-slot="data">
      <devices :manufactureId = "data.factId"></devices>
    </manufacturer>
  
  </div>
</template>

<script>
import Manufacturer from './components/Manufacturer.vue';
import Devices from './components/Devices.vue';
export default {
  name: 'App',
  components: {
    Manufacturer: Manufacturer,
    Devices: Devices,
  },
};
</script>

<style></style> -->

<template>
  <router-view></router-view>
</template>

<script>
export default {
  name: "App",
};
</script>
