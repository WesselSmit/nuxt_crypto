<template>
  <header class="header">
    <nav class="header__inner">
      <nuxt-link to="/" class="header__logo">Crypto Watch</nuxt-link>

      <ul class="header__list">
        <li class="header__item">
          <nuxt-link to="/" class="header__link">Home</nuxt-link>
        </li>
        <li class="header__item">
          <nuxt-link to="/exchanges" class="header__link">Exchanges</nuxt-link>
        </li>
        <li class="header__item">
          <nuxt-link to="/coins" class="header__link">Coins</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss">
  .header {
    position: relative;
    z-index: 100;
    margin-bottom: $space-xl;
    background-color: $clr-accent;

    &__inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      max-width: $site-width;
      margin: auto;
    }

    &__logo {
      margin: 0;
      font-size: 28px;
      color: $clr-text;
      text-decoration: none;

      &:hover,
      &:focus {
        color: $clr-white;
      }
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
        color: $clr-white;
      }
    }
  }
</style>
