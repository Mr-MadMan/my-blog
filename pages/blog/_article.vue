<template>
  <div class="ac-main-wrap">
    <article>
      <h1>文章标题</h1>
      <div class="author-info">作者: madman</div>
      <div class="ac-content" />
    </article>
  </div>
</template>

<script>
export default {
  components: {
  },
  props: {
  },
  asyncData({ params }) {
    const { id, title } = params
    return {
      article: {
        id,
        title
      }
    }
  },
  data() {
    return {
      article: {}
    }
  },
  head() {
    return {
      title: this.article.title,
      meta: [
        // { hid: 'description', name: 'description', content: desc }
        // { name: 'keywords', content: keywords }
      ]
    }
  },
  created() {
  },
  mounted() {
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
  .ac-main-wrap {
    width: 820px;
    max-width: 100%;
    margin: 0 auto;
  }
</style>
