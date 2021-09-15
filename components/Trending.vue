<template>
  <section class="trending">
    <h2>Trending currencies</h2>

    <p v-if="$fetchState.pending">Loading...</p>
    <ul v-else-if="!$fetchState.pending && currencies">
      <li v-for="currency in currencies" :key="currency.name">
        <nuxt-link :to="'/coins/' + currency.id">
        <article>
          <h3>{{ currency.name }}</h3>
          <h4>$ {{ currency.usd }}</h4>
          <p>Last updated on: {{ currency.last_updated_at }}</p>
        </article>
      </nuxt-link>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      currencies: []
    }
  },
  async fetch() {
    const res = await fetch('https://api.coingecko.com/api/v3/simple/price?ids=bitcoin%2Cethereum&vs_currencies=usd&include_market_cap=true&include_last_updated_at=true')
    const data = await res.json()
    const formattedData = Object.entries(data).map(currencyObj => {
      currencyObj[1].name = currencyObj[0]
      currencyObj[1].id = currencyObj[0]

      const lastUpdatedDate = new Date(1504095567183).toLocaleDateString('nl')
      const lastUpdatedTime = new Date(1504095567183).toLocaleTimeString('nl')
      currencyObj[1].last_updated_at = lastUpdatedDate + ' - ' + lastUpdatedTime

      return currencyObj[1]
    })
    this.currencies = formattedData
  },
  fetchOnServer: false,
}
</script>

<style lang="scss">
  .trending {

  }
</style>
