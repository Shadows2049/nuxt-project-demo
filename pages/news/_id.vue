<template>
  <div class="container">
    <h1>Dynamic</h1>
    <nuxt-link :to="{ name: 'index' }">Home</nuxt-link>
    <h2>ID is: {{ $route.params.id }}</h2>
  </div>
</template>

<script>
export default {
  validate({ params }) {
    console.log(params.id)
    return params.id === '456'
  },
  mounted() {
    this.$toast.show('Toast testing')
  },
}
</script>
