<template>
  <main class="exchange">
    <h1>{{ exchange.name }}</h1>

    <nuxt-img
      :src="exchange.image"
      :quality="80"
      :width="51"
      :height="51"
      class="exchange__image"
    />
  </main>
</template>

<script>
  export default {
    async asyncData({ params: { id } }) {
      const res = await fetch('https://api.coingecko.com/api/v3/exchanges/' + id)
      const data = await res.json()
      return { exchange: data }
    },
  }
</script>

<style lang="scss">
  .exchange {

  }
</style>
