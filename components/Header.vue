<template>
  <header class="header">
    <nav class="header__inner">
      <h6 class="header__title">Crypto Watch</h6>

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

<style lang="scss">
  .header {
    margin-bottom: $space-xl;
    border-bottom: $border-normal;

    &__inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      max-width: $site-width;
      margin: auto;
    }

    &__title {
      margin: 0;
      font-size: 28px;
    }

    &__list {
      display: flex;
      justify-content: space-between;
    }

    &__item {
      padding: $space-md;

      &:last-child {
        padding-right: 0;
      }
    }

    &__link {
      color: $clr-text;
      line-height: .9;

      &:hover {
        color: $clr-accent;
      }
    }
  }
</style>
