<template>
    <div @click="goToDetails()"
      class="item-list flex flex-col flex-grow my-8 bg-white shadow rounded-lg p-6"
    >
      <h2 class="text-2xl leading-7 font-semibold">
        {{ vulnerability.title }}
      </h2>
      <p class="mt-3 text-gray-600">
        {{ vulnerability.description }}
      </p>
    </div>
</template>

<script>
import { mapActions } from 'vuex'

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
    ...mapActions(['setCurrentVulnerability']),


    goToDetails(){
    this.setCurrentVulnerability(this.vulnerability)
      this.$router.push({
        name: 'details' 
      })
    }

  }
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
