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
    async asyncData({ params: { id }, redirect }) {
      const res = await fetch('https://api.coingecko.com/api/v3/exchanges/' + id)
      const data = await res.json()

      if (data?.error) {
        redirect('/exchanges')
      }

      return { exchange: data }
    },
    head() {
      console.log(this.exchange)
      return {
        title: this.exchange.name,
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.exchange.description
          }
        ]
      }
    }
  }
</script>

<style lang="scss">
  .exchange {

  }
</style>
