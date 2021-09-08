<template>
  <header class="header">
    <nav>
      <ul>
        <li>
          <nuxt-link to="/" class="header__link">Home</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/exchanges" class="header__link">Exchanges</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/coins" class="header__link">Coins</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss">
  .header {
    &__link {
      color: $clr-text;
      text-decoration: none;
    }
  }
</style>
