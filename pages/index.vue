<template>
  <div class="container">
    <ul>
      <li style="font-size: 40px">
        <nuxt-link :to="{ name: 'about' }">About</nuxt-link>
        <nuxt-link :to="{ name: 'news', params: { xxid: 1111 } }"
          >News</nuxt-link
        >
        <a href="/news/456"> Dynamic</a>
        <a href="/aaawad"> Error Page</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>
