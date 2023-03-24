<template>
    <div class="timer">
      <div class="timer__texts">
        <div class="timer__input">

          <input @keydown.enter="isShowing=false" v-show="isShowing"  v-model="count" placeholder="input time count">
        </div>
        <div style="position: absolute" class="timer__rime">
            <span style=" left: 90px" @click="isShowing = !isShowing">{{count}}</span>
        </div>
      </div>

      <div class="timer__btns">
      <button   @click="timerEnabled = !timerEnabled" >
        <p v-if="timerEnabled">
          ⏸
        </p><p v-if="!timerEnabled">
        ⏵
      </p></button>
      <button @keydown.esc="stop" @click="stop">⏹</button>
      </div>
    </div>
</template>

<script>
export default {
  name: "main-timer",
  data() {
    return {
      timerEnabled: false,
      count:  60,
      isShowing: false,
    }
  },
  watch: {
    timerEnabled(value) {
      if (value) {
        setTimeout(() => this.count--, 1000)
      }
    },
    count: {
      handler(value) {
        if (value > 0 && this.timerEnabled) {
          setTimeout(() => this.count--, 1000)
        }
      }
    }
  },

  methods: {
    stop() {
      this.count = 60;
      this.timerEnabled = false;
    }
  }
}
</script>

<style lang="scss">
@import "timer";
</style>