<template>
  <div id="app">
    <home />
    <router-view/>
  </div>
</template>
<script>
import home from './views/Home'
export default {
  name: 'App',
  data () {
    return {}
  },
  components: {
    home
  }
}
</script>
<style>
</style>
