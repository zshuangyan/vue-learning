<template>
  <h3>{{ title }}</h3>
</template>

<style scoped>
</style>

<script>
export default {
  props: ['state'],
  data () {
    return {
      title: this.state
    }
  }
}
</script>
