<template>
  <div class="column">
    <div
      class="is-flex is-align-itemns-center is-justify-content-space-between"
    >
      <StopWatch :secondsTime="secondsTime" />
      <button class="button" @click="start" :disabled="startTimer">
        <span class="icon">
          <i class="fas fa-play"></i>
        </span>
        <span>Play</span>
      </button>
      <button class="button" @click="pause" :disabled="!startTimer">
        <span class="icon">
          <i class="fas fa-stop"></i>
        </span>
        <span>Stop</span>
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";

export default defineComponent({
  name: "TimerTask",
  emits:["timerEnded"],
  components: {
    StopWatch,
  },
  data() {
    return {
      secondsTime: 0,
      secondsPause: 0,
      startTimer: false
    };
  },
  methods: {
    start() {
      this.startTimer = true
      this.secondsPause = setInterval(() => {
        this.secondsTime += 1;
      }, 1000);
    },
    pause() {
      this.startTimer = false
      clearInterval(this.secondsPause);
      this.$emit("timerEnded", this.secondsTime)
      this.secondsTime = 0
    },
  },
});
</script>
