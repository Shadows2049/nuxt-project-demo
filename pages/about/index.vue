<template>
  <div class="container">
    <h1>About</h1>
    <h1>{{ info.data.title }}</h1>
    <h1>{{ info.data.desc }}</h1>
    <nuxt-link :to="{ name: 'index' }">Home</nuxt-link>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  asyncData() {
    return axios({
      methods: 'get',
      url: '/tempData.js',
    }).then((_data) => {
      console.log(_data.data)
      return {
        info: _data.data,
      }
    })
  },
  head() {
    return {
      title: this.info.msg,
    }
  },
}
</script>
