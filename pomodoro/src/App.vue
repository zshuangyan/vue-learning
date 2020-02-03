<template>
  <div id="app" class="container">
    <h2>
      <span>Pomodoro</span>
      <span>{{ state }}</span>
      <controls-component  :state="state" @update="onStateUpdate"></controls-component>
    </h2>
    <state-title-component :state="state"></state-title-component>
    <countdown-component></countdown-component>
    <kittens-component></kittens-component>
  </div>
</template>

<style scoped>
</style>

<script>
import ControlsComponent from './components/ControlsComponent'
import CountdownComponent from './components/CountdownComponent'
import KittensComponent from './components/KittensComponent'
import StateTitleComponent from './components/StateTitleComponent'
import STATES from './variable'

export default {
  components: {
    ControlsComponent,
    CountdownComponent,
    KittensComponent,
    StateTitleComponent
  },
  methods: {
    onStateUpdate (newState) {
      this.state = newState
    }
  },
  data () {
    return {
      state: STATES.STOPPED
    }
  }

}
</script>
