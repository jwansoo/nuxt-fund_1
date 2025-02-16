<template>
  <form @submit.prevent="user.login">
    <h1 class="bg-blue-500 text-white rounded-xl w-16 px-2 py-0.5 text-center font-bold text-xl mt-2 ml-2">Login</h1>
    <label for="">
      Username
      <input type="text" class="bg-gray-400" />
    </label>
    <label for="">
      Password
      <input type="password" class="bg-gray-400">
    </label>
    <button>Login</button>
  </form>
</template>

<script setup>
const user=useUser()
definePageMeta({
  layout:'plain'
})
</script>

<style scoped>

</style>