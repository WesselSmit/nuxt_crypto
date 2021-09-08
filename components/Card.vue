<template>
  <article class="card">
    <nuxt-img
      v-if="image"
      :src="image"
      :quality="80"
      :width="50"
      class="card__image"
    />

    <h2 class="card__title">{{ title }}</h2>

    <p
      v-if="body"
      class="card__body">
      {{ body }}
    </p>
  </article>
</template>

<script>
  export default {
    props: {
      image: {
        type: String,
        default: null
      },
      title: {
        type: String,
        required: true
      },
      body: {
        type: String,
        default: null
      }
    }
  }
</script>

<style lang="scss">
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    padding: $space-sm;
    border: 1px solid $clr-gray;
    border-radius: 10px;

    &:hover,
    &:focus {
      border-color: $clr-accent;
    }

    &__image {
      margin-bottom: $space-sm;
    }

    &__title {
      font-weight: 400;
      font-size: 12px;
      text-align: center;
      word-break: break-word;
    }
  }
</style>
