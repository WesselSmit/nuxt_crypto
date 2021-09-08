<template>
  <main class="coins">
    <h1 class="coins__title">Coins</h1>
    <p>This is a list of all the crypto currencies in the API.</p>

    <List :data="coins" :link-base="'/coins/'" />
  </main>
</template>

<script>
  export default {
    async asyncData() {
      const res = await fetch('https://api.coingecko.com/api/v3/coins/markets?vs_currency=eur')
      const data = await res.json()
      return { coins: data }
    },
  }
</script>

<style lang="scss">
  .coins {
    margin-bottom: $space-xl;

    &__title {
      margin-bottom: $space-xsm;
    }
  }
</style>
