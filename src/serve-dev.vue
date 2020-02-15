<script>
import Vue from 'vue';
import vueIntervalLoop from '@/vue-interval-loop.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    vueIntervalLoop
  }
});
</script>

<template>
  <div id="app">
    <vue-interval-loop />
  </div>
</template>
