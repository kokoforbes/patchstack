<template>
  <div class="bg-gray-100 min-h-screen pt-12">
    <div
      class="container mx-auto flex flex-col justify-center"
    >
        <div
          class="flex justify-between p-5 items-center"
        >
          <button
            class="text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
            @click="$router.back()"
          >
            Back
          </button>

          <button
            class="text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
            @click="goToEdit()"
          >
            Edit
          </button>
        </div>

        <div class="flex flex-col flex-grow mt-8 bg-white shadow rounded-lg p-6 mx-2">
          <h2 class="text-2xl leading-7 font-semibold">
            {{ getVulnerability.title }}
          </h2>
          <p class="mt-3 text-gray-600">
            {{ getVulnerability.description }}
          </p>
        </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'


export default {
  name: 'Details',
  data() {
    return {
      vulnerability: {},
    }
  },

  computed: {
    ...mapGetters(['getVulnerability']),
  },

  methods: {
    goToEdit() {
      this.$router.push({
        name: 'edit',
      })
    },
  },
}
</script>

<style></style>
