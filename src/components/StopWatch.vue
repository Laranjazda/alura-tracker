<template>
  <section>
    <strong>{{ secondsTransform }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "StopWatch",
  props: {
    secondsTime: {
      type: Number,
      default: 0,
    },
  },

  computed: {
    secondsTransform(): string {
      return new Date(this.secondsTime * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>
