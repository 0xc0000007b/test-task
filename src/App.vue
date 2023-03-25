<script>



import MainTimer from "@/components/timer-main/timer.vue";


export default {
  components: {MainTimer},

  data() {
    return {
      times: [ 0],
      aaa: null
    }
  },
}

</script>

<template>
 <div class="wrapper">
    <div class="timers">
      <ul >
        <li v-for="time in times" :key="time">
          <MainTimer v-bind:timer_data="time"></MainTimer>
        </li>
      </ul>
    </div>
  <div class="adding-table">


    <button @click="times.push(0)">+</button>
  </div>
 </div>
</template>

<style lang="scss">

@import "app";
</style>
