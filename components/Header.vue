<template>
  <header class="header">
    <nav>
      <ul class="header__list">
        <li class="header__item">
          <nuxt-link :to="'/'" class="header__link">Home</nuxt-link>
        </li>
        <li class="header__item">
          <nuxt-link :to="'/exchanges'" class="header__link">Exchanges</nuxt-link>
        </li>
        <li class="header__item">
          <nuxt-link :to="'/coins'" class="header__link">Coins</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss">
  .header {
    margin-bottom: $space-xl;
    border-bottom: $border-normal;

    &__list {
      display: flex;
      justify-content: flex-end;
      max-width: $site-width;
      margin: auto;
    }

    &__item {
      padding: $space-md;

      &:last-child {
        padding-right: 0;
      }
    }

    &__link {
      color: $clr-text;
      text-transform: uppercase;
      text-decoration: none;

      &:hover {
        color: $clr-accent;
      }
    }
  }
</style>
