<template>
  <div id="post">
    <div
      class="post-thumbnail"
      :style="{ backgroundImage: 'url(' + image + ')' }"
    ></div>
    <section class="post-content">
      <h1>{{ title }}</h1>
      <p>{{ content }}</p>
    </section>
  </div>
</template>

<script>
export default {
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories/blog/' + context.params.postId, {
        version: 'draft',
      })
      .then((res) => {
        console.log(res.data)
        return {
          image: res.data.story.content.thumbnail,
          title: res.data.story.content.title,
          content: res.data.story.content.content,
        }
      })
  },
}
</script>

<style scoped>
.post-thumbnail {
  width: 100%;
  height: 50vh;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
}

.post-content {
  text-align: center;
  width: 80%;
  max-width: 500px;
  margin: auto;
}

#post-content p {
  white-space: pre;
}
</style>
