<template>
  <div id="app">
    <headerContent />
    <mainContent />
  </div>
</template>

<script>
import headerContent from './components/header.vue'
import mainContent from './components/main.vue'

export default {
  name: 'App',
  components: {
    headerContent,
    mainContent,
  }
}
</script>

<style lang="scss">

</style>
