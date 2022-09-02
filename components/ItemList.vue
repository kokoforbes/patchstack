<template>
  <nuxt-link
    :to="{ name: 'details', params: { vulnerability: this.vulnerability } }"
  >
    <div
      class="item-list flex flex-col flex-grow my-8 bg-white shadow rounded-lg p-6"
    >
      <h2 class="text-2xl leading-7 font-semibold">
        {{ vulnerability.title }}
      </h2>
      <p class="mt-3 text-gray-600">
        {{ vulnerability.description }}
      </p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'ItemList',

  props: {
    vulnerability: {
      type: Object,
      default: () => {
        return {}
      },
    },
  },
}
</script>

<style lang="scss" scoped>
.item-list {
  max-width: 50rem;
  width: 100%;

  p {
    width: 15rem;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    @media (min-width: 500px) {
      width: 30rem;
    }
  }
}
</style>
