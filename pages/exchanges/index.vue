<template>
  <main class="exchanges">
    <h1 class="exchanges__title">Exchanges</h1>
    <p>This is a list of all the crypto currency list in the API.</p>

    <List :data="exchanges" :link-base="'/exchanges/'" />
  </main>
</template>

<script>
  export default {
    async asyncData() {
      const res = await fetch('https://api.coingecko.com/api/v3/exchanges')
      const data = await res.json()
      return { exchanges: data }
    },
  }
</script>

<style lang="scss">
  .exchanges {
    margin-bottom: $space-xl;

    &__title {
      margin-bottom: $space-xsm;
    }
  }
</style>
