<template>
  <div>
    <h1>{{ msg }}</h1>
    <nuxt-link :to="{ name: 'index' }">Home</nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: 'Error Page',
    }
  },
}
</script>
