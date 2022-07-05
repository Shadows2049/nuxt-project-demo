<template>
  <section id="about-page">
    <div class="container">
      <h1>{{ title }}</h1>
      <p>{{ content }}</p>
    </div>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories/about', {
        version: 'draft',
      })
      .then((res) => {
        return {
          title: res.data.story.content.title,
          content: res.data.story.content.content,
        }
      })
  },
}
</script>
<style>
#about-page {
  width: 80%;
  margin: auto;
}
#about-page p {
  white-space: pre;
}
</style>
