<template>
  <div class="ui grid dashboard" v-if="coin">
    <div class="sixteen wide column">
      <img :src="`https://chasing-coins.com/api/v1/std/logo/${coin.symbol}`" />
      <h1 class="ui header">{{coin.name}} <span>{{coin.symbol}}</span></h1>
      <a class="ui orange label">Rank {{coin.rank}}</a>
      <p class="dashboard__trading">Currently trading at <span class="segment__primary">{{formatCurrency(coinQuotes.price)}}</span></p>
      <p class="dashboard__market-cap">with a Market Cap of <span class="segment__primary">{{formatCurrency(coinQuotes.market_cap)}}</span></p>
      <div class="ui cards">
        <div class="card">
          <div class="content">
            <div class="header">Volume(24hr)</div>
            <div class="meta">Volume that has been traded in the last 24hrs</div>
            <div class="description">
              {{formatCurrency(coinQuotes.volume_24h)}}
            </div>
          </div>
        </div>
        <div class="card">
          <div class="content">
            <div class="header">1hr change</div>
            <div class="meta">Price change in the last hour</div>
            <div
              class="description"
              :class="[isValuePositive(coinQuotes.percent_change_1h) ? 'segment__positive' : 'segment__negative']"
            >
              {{formatNumber(coinQuotes.percent_change_1h)}} %
            </div>
          </div>
        </div>
        <div class="card">
          <div class="content">
            <div class="header">24hr change</div>
            <div class="meta">Price change in the last 24 hours</div>
            <div
              class="description"
              :class="[isValuePositive(coinQuotes.percent_change_24h) ? 'segment__positive' : 'segment__negative']"
            >
              {{formatNumber(coinQuotes.percent_change_24h)}} %
            </div>
          </div>
        </div>
        <div class="card">
          <div class="content">
            <div class="header">7 day Change</div>
            <div class="meta">Price change in the last 7 days</div>
            <div
              class="description"
              :class="[isValuePositive(coinQuotes.percent_change_7d) ? 'segment__positive' : 'segment__negative']"
            >
              {{formatNumber(coinQuotes.percent_change_7d)}} %
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import utils from '@/utils'
export default {
  name: 'CoinDetailsPage',
  props: ['slug'],
  computed: {
    coin() {
      return this.$store.getters.coinDataFromSlug(this.slug)
    },
    coinQuotes() {
      return this.$store.getters.coinDataFromSlug(this.slug).quotes.USD
    }
  },
  created() {
    this.formatCurrency = utils.formatCurrency
    this.formatNumber = utils.formatNumber
    this.isValuePositive = utils.isValuePositive
  }
}
</script>

<style src="@/assets/styles/coin-details-page.css">
</style>
