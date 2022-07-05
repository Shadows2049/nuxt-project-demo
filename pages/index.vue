<template>
  <section id="posts">
    <postPreview
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :excerpt="post.previewText"
      :thumbnailImage="post.thumbnailUrl"
      :id="post.id"
    />
  </section>
</template>

<script>
import postPreview from '@/components/Blog/postPreview.vue'
export default {
  name: 'IndexPage',
  components: {
    postPreview,
  },
  asyncData(context) {
    return context.app.$storyapi
      .get('cdn/stories', {
        version: 'draft',
        starts_with: 'blog/',
      })
      .then((res) => {
        return {
          posts: res.data.stories.map((bp) => {
            return {
              id: bp.slug,
              title: bp.content.title,
              previewText: bp.content.summary,
              thumbnailUrl: bp.content.thumbnail,
            }
          }),
        }
      })
  },
  /* data() {
    return {
      posts: [
        {
          title: 'Alesana',
          previewText: 'Where Myth Fades To Legend',
          thumbnailUrl: '/WMFTL.jpg',
          id: 'demo',
        },
        {
          title: 'Alesana',
          previewText: 'Where Myth Fades To Legend',
          thumbnailUrl: '/WMFTL.jpg',
          id: 'demo2',
        },
      ],
    }
  },*/
}
</script>

<style scoped>
#posts {
  padding-top: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 35rem) {
  #posts {
    flex-direction: row;
  }
}
</style>
