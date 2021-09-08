<template>
  <main class="exchanges">
    <h1 class="exchanges__heading">Exchanges</h1>

    <ul class="exchanges__list">
      <li
        v-for="exchange in exchanges"
        :key="exchange.id"
        class="exchanges__item"
      >
        <nuxt-link to="">
          <article class="exchanges__card">
            <h3 class="exchanges__title">{{ exchange.name }}</h3>
            <nuxt-img :src="exchange.image"></nuxt-img>
          </article>
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
    console.log(data)
    return { exchanges: data }
  },
}
</script>

<style lang="scss">

</style>
