<template>
  <div id="app">
    <div id="nav">
      <app-header/>
    </div>
    <router-view/>
  </div>
</template>

<script>
import AppHeader from '@/app-header'

export default {
  name: 'App',
  components: {
    'app-header': AppHeader
  },
  created() {
    this.$store.dispatch('getCoins')
    this.$store.dispatch('getMarketData')
  }
}
</script>

<style src="@/assets/styles/app.css">
</style>