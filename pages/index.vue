<template>
  <div class="bg-gray-100 body-font">
    <div
    class="container mx-auto flex px-5 py-16 items-center justify-center flex-col min-h-screen items-end"
  >
    <div class="header">
      <button
        class="text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
        @click="goToCreate()"
      >
        Create
      </button>
    </div>

    <div class="flex flex-col justify-center">
      <div v-for="(vul, index) in getVulnerabilities" :key="index">
        <ItemList :vulnerability="vul" />
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'IndexPage',

  computed: {
    ...mapGetters(['getVulnerabilities']),
  },

  methods: {
    goToCreate() {
      this.$router.push({
        path: '/create',
      })
    },
  },
}
</script>
