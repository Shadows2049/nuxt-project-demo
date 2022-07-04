<template>
  <div class="container">
    <h1>News</h1>
    <nuxt-link :to="{ name: 'index' }">Home</nuxt-link>
    <h2>ID is: {{ $route.params.xxid }}</h2>
  </div>
</template>

<script>
export default {}
</script>
