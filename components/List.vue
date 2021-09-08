<template>
  <section class="list">
    <ul class="list__list">
      <li
        v-for="item in data"
        :key="item.id"
        class="list__item"
      >
        <nuxt-link :to="linkBase + item.id">
          <Card
            :image="item.image"
            :title="item.name"
          />
        </nuxt-link>
      </li>
    </ul>
  </section>
</template>

<script>
  export default {
    props: {
      data: {
        type: Array,
        required: true
      },
      linkBase: {
        type: String,
        required: true
      }
    }
  }
</script>

<style lang="scss">
  .list {
    &__list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
      grid-gap: $space-md;
      margin-top: $space-md;
    }
  }
</style>
