<template>
  <div
    class="relative  items-top  min-h-screen bg-gray-100 sm:items-center sm:pt-0"
  >
<div class="header">
  <button @click="goToCreate()">Create</button>
</div>


    <div class="flex flex-col justify-center">
      <ItemList />
      <Tutorial />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',

  methods: {
    goToCreate(){
      this.$router.push({
        path: '/create'
      })
    }
  }
}
</script>
