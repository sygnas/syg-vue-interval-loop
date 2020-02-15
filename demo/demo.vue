<script>
import Vue from 'vue';
import vueIntervalLoop from '../dist/vue-interval-loop.esm';

export default Vue.extend({
  name: 'Demo',
  components: {
    vueIntervalLoop
  }
});
</script>

<template>
  <div id="app">
    <vue-interval-loop v-slot:default="slotProps">
      <p v-if="slotProps.now === 0">This is 0.</p>
      <p v-else-if="slotProps.now === 1">This is 1.</p>
      <p v-else>This is other {{slotProps.now}}.</p>
    </vue-interval-loop>
  </div>
</template>
