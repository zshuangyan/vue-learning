<template>
  <div>
    <button title="start">
      <i class="glyphicon glyphicon-play" @click="start()"></i>
    </button>
    <button title="pause">
      <i class="glyphicon glyphicon-pause" @click="pause()"></i>
    </button>
    <button title="stop">
      <i class="glyphicon glyphicon-stop" @click="stop()"></i>
    </button>
  </div>
</template>

<style scoped>
</style>

<script>
import STATES from '../variable'
export default {
  props: ['state'],
  methods: {
    start () {
      if (this.state !== STATES.STARTED) {
        const curState = STATES.STARTED
        console.log(this.state)
        this.$emit('update', curState)
      }
    },
    pause () {
      if (this.state === STATES.STARTED) {
        this.state = STATES.PAUSED
      }
    },
    stop () {
      if (this.state === STATES.STARTED) {
        this.state = STATES.STOPPED
      }
    }
  }
}
</script>
