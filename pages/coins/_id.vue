<template>
  <main class="coin">
    <h1>{{ coin.name }} ({{ coin.symbol }})</h1>

    <div class="coin__inner">
      <div>
        <p
          class="coin__description"
          :class="{'coin__description--collapsed': collapsed}"
          v-html="coin.description.en"
        ></p>
        <button
          class="coin__button"
          @click="collapse"
        >{{ collapseText }}</button>
      </div>

      <nuxt-img
        :src="coin.image.large"
        :quality="80"
        :width="200"
        :height="200"
        class="coin__image"
      />
    </div>
  </main>
</template>

<script>
  export default {
    async asyncData({ params: { id } }) {
      const res = await fetch('https://api.coingecko.com/api/v3/coins/' + id)
      const data = await res.json()
      return { coin: data }
    },
    data() {
      return {
        collapsed: true
      }
    },
    computed: {
      collapseText() {
        return 'Show' + this.collapsed ? 'More' : 'Less'
      }
    },
    methods: {
      collapse() {
        this.collapsed = !this.collapsed
      }
    }
  }
</script>

<style lang="scss">
  .coin {
    &__inner {
      display: flex;
    }

    &__description {
      margin-bottom: $space-xsm;

      a {
        color: $clr-text;
        text-decoration: underline;
        text-decoration-color: $clr-accent;
        text-decoration-thickness: 2px;

        &:hover {
          color: $clr-accent;
        }
      }

      &--collapsed {
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
      }
    }

    &__button {
      color: $clr-accent;
      cursor: pointer;
    }

    &__image {
      margin-left: $space-xl;
    }
  }
</style>
