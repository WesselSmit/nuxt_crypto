<template>
  <main class="exchanges">
    <h1>Exchanges</h1>

    <ul class="exchanges__list">
      <li
        v-for="exchange in exchanges"
        :key="exchange.id"
        class="exchanges__item"
      >
        <nuxt-link :to="'/coin/' + exchange.id">
          <Card
            :image="exchange.image"
            :title="exchange.name"
            :body="exchange.description"
          />
        </nuxt-link>
      </li>
    </ul>
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

  &__list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    grid-gap: $space-md;
  }
}
</style>
