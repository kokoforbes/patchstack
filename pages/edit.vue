<template>
  <div class="bg-gray-100 body-font min-h-screen pt-12">
    <div class="container mx-auto flex flex-col w-full px-6 items-end sm:w-3/5">
      <div class="relative flex-grow w-full">
        <label for="title" class="leading-7 text-gray-600">Title</label>
        <input
          v-model="title"
          type="text"
          id="title"
          name="title"
          class="w-full bg-gray-100 bg-opacity-50 rounded border border-gray-300 focus:border-indigo-500 focus:bg-transparent focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
        />
      </div>
      <div class="relative flex-grow w-full mt-6">
        <label for="description" class="leading-7 text-gray-600"
          >Description</label
        >
        <textarea
          v-model="description"
          id="description"
          name="description"
          class="w-full bg-gray-100 bg-opacity-50 rounded border border-gray-300 focus:border-indigo-500 focus:bg-transparent focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
        ></textarea>
      </div>

      <div class="flex w-full justify-between p-5 mt-6">
        <button
          class="text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
          @click="$router.back()"
        >
          Back
        </button>

        <button
          class="text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
          @click="update()"
        >
          Update
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'

export default {
  name: 'Edit',

  computed: {
    ...mapGetters(['getVulnerability']),
  },

  computed: {
    title: {
      get() {
        return this.$store.state.vulnerability.title
      },
      set(value) {
        this.$store.commit('UPDATE_TITLE', value)
      },
    },

    description: {
      get() {
        return this.$store.state.vulnerability.description
      },
      set(value) {
        this.$store.commit('UPDATE_DESCRIPTION', value)
      },
    },
  },

  methods: {
    ...mapActions(['updateVulnerability']),

    update() {
     this.updateVulnerability()

      setTimeout(() => {
        this.$router.push('/details')
      }, 1000)
    },
  },
}
</script>

<style></style>
