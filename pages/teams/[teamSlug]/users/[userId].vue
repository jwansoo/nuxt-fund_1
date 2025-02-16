<template>
  <div>
    {{ message }}
  </div>
</template>

<script setup lang="ts">
const route=useRoute()
const message=computed(()=>`I'm on team ${route.params.teamSlug} and my user id is ${route.params.userId}`)
</script>

<style scoped>

</style>