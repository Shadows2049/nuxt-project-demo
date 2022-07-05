<template>
  <div>
    <theHeader />
    <main class="main-content">
      <nuxt />
    </main>
  </div>
</template>

<script>
import theHeader from '@/components/theHeader/theHeader.vue'

export default {
  components: {
    theHeader,
  },
}
</script>
<style>
* {
  box-sizing: border-box;
}

body {
  font-family: 'Raleway', sans-serif;
  margin: 0;
}
.main-content {
  margin-top: 4.5rem;
}
</style>
