<template>
  <main class="home">
    <h1>Crypto Watch</h1>

    <p class="home__intro">This website was made as an experiment to try out <a href="https://nuxtjs.org" target="_blank" class="home__link">Nuxt.js</a>, It consumes the <a href="https://www.coingecko.com/en/api/documentation" target="_blank" class="home__link">Coingecko API</a> for all data necessary to function.</p>

    <p>Check the <nuxt-link to="/exchanges" class="home__link">/exchanges</nuxt-link> and <nuxt-link to="/coins" class="home__link">/coins</nuxt-link> pages for more content.</p>

    <Trending />
  </main>
</template>

<script>
  export default {
    head() {
      return {
        title: 'Home',
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: 'Crypto watch is an experiment to try out Nuxt.js.'
          }
        ]
      }
    }
  }
</script>

<style lang="scss">
  .home {
    margin: $space-xl 0;

    &__intro {
      margin-bottom: $space-md;
    }

    &__link {
      color: $clr-text;
      text-decoration: underline;
      text-decoration-color: $clr-accent;
      text-decoration-thickness: 2px;

      &:hover {
        color: $clr-accent;
      }
    }
  }
</style>
