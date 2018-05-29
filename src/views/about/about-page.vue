<template>
  <div class="ui grid about">
		<h1 class="ui header">SimpleCrypto</h1>
		<div class="content">
			<p>SimpleCrypto displays market cap rankings, price, details and more for the top
			100 largest cryptocurrencies based on overall market cap. Built with
      <a href="https://vuejs.org/" target="_blank">Vue</a>, <a href="https://router.vuejs.org/en/" target="_blank">Vue Router</a>,
      <a href="https://vuex.vuejs.org/en/" target="_blank">Vuex</a>, and deployed on <a href="https://www.heroku.com/" target="_blank">Heroku.</a>;
			<p>
				Cryptocurrency data obtained from the <a href="https://coinmarketcap.com/api/" target="_blank">Coinmarketcap API</a>.
        Cryptocurrency logo images obtained from the <a href="https://chasing-coins.com/api" target="_blank">Chasing Coins API</a>.
			</p>
		</div>
	</div>
</template>

<script>
export default {
  name: 'AboutPage'
}
</script>

<style src="@/assets/styles/about-page.css">
</style>
