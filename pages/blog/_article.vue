<template>
  <div class="ac-main-wrap">
    <article>
      <h1>文章标题</h1>
      <div class="author-info">
        <span>2023年2月23日</span>
        <span style="margin-left: 10px">23次阅读</span>
        <span style="margin-left: 10px">madman</span>
      </div>

      <div class="ac-content">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum qui excepturi labore recusandae corporis architecto ducimus ipsam assumenda illo quibusdam soluta suscipit delectus, consequuntur sapiente magni voluptatem rerum. Voluptate, accusantium?</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis veritatis accusamus expedita rerum. Obcaecati repellendus exercitationem inventore esse officiis repellat nulla earum doloribus. Ab cum quisquam impedit excepturi officia eius?</p>

        <ol>
          <li>123</li>
          <li>15</li>
          <li>23</li>
        </ol>

      </div>
    </article>
  </div>
</template>

<script>
export default {
  components: {
  },
  layout: 'base',
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
    height: 100%;
    margin: 2rem auto;
    padding: 2rem 1.6rem 1.6rem 1.6rem;
    background-color: #fff;
    border-radius: 4px;

    h1 {
      margin-top: 0;
    }
  }

  .author-info {
    margin-bottom: 15px;
    color: #8a919f;
  }

  .ac-content {
    line-height: 1.6;
  }
</style>
