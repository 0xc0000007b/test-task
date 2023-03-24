<script>

import {defineComponent} from "vue";
import MainTimer from "@/components/timer-main/timer.vue";

export default defineComponent({
  components: {MainTimer}
})
</script>

<template>
  <div class="wrapper">
      <main-timer />
  </div>
</template>

<style lang="scss">

@import "app";
</style>
