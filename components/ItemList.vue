<template>
  <div
    class="item-list my-8 bg-white overflow-hidden shadow sm:rounded-lg p-6"
    @click="viewVulnerability()"
  >
    <h2 class="text-2xl leading-7 font-semibold">
      Welcome to your Nuxt Application
    </h2>
    <p class="mt-3 text-gray-600">
      We recommend you take a look at the, whether you are new or have previous
      experience with the framework.<br />
    </p>
  </div>
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

  methods: {
    viewVulnerability() {
      this.$router.push({
        path: `/edit`,
        append: true,
        params: {
          vulnerability: this.vulnerability,
        },
      })
    },
  },

  mounted() {},
}
</script>

<style lang="scss">
.item-list {
  max-width: 50rem;
  width: 100%;
  // height: 6rem;
}
</style>
