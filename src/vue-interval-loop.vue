<script>
export default {
  name: "vueIntervalLoop",
  props: {
    max: {
      type: Number,
      default() {
        return 3;
      }
    },
    start: {
      type: Number,
      default() {
        return 0;
      }
    },
    delay: {
      type: Number,
      default() {
        return 1000;
      }
    }
  },
  data() {
    return {
      now: this.start,
      intervalId: null
    };
  },
  mounted() {
    this.intervalId = setInterval(() => {
      this.now = (this.now + 1) % this.max;
    }, this.delay);
  },
  beforeDestroy() {
    clearInterval(this.intervalId);
  },
};
</script>

<template>
  <div>
    <slot :now="now" />
  </div>
</template>
