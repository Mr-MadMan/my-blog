<template>
  <!-- <div class="post-item md:w-8/12 lg:w-auto"> -->
  <div class="post-item">
    <div class="post-item-top" @click="handleGotoDetail">
      <img class="cover" src="https://picsum.photos/400/300" alt="cover" />
      <div>
        <p class="post-item-title">{{ acData.title }}</p>
        <p
          class="post-item-desc"
        >貌似从前几年，前后端分离逐渐就开始流行起来，把一些渲染计算的工作抛向前端以便减轻服务端的压力，但为啥现在又开始流行在服务端渲染了呢？如vue全家桶或者react全家桶，都推荐通过服务端渲染来实现路由。搞得我们慌得不行，不禁让我想起一句话：从来没有任何一门语言的技术栈像Javascript一样，学习者拼尽全力也不让精通。没办法，流行，咱们就得学！</p>
      </div>
    </div>
    <div class="post-item-bottom">
      <span class="date">{{ date }}</span>
      <span>{{ acData.commentCount }}条评论</span>
      <span>{{ acData.readCount }}次阅读</span>
      <span>{{ acData.likes }}人点赞</span>
      <span>{{ acData.author }}</span>

      <!-- <nuxt-link :to="`/blog/2`">阅读全文</nuxt-link> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'PostItem',
  components: {
  },
  props: {
    acData: {
      type: Object,
      default: () => {}
    }
  },

  data() {
    return {}
  },
  computed: {
    date() {
      const dateTmp = this.acData.date.split('-')
      return dateTmp[0] + '年' + dateTmp[1] + '月' + dateTmp[2] + '日'
    }
  },
  created() {
  },
  mounted() {
  },
  methods: {
    handleGotoDetail() {
      this.$router.push({ name: 'blog-article', params: { id: this.acData.id, title: this.acData.title } })
    }
  }
}
</script>

<style lang="scss" scoped>
  .post-item {
    background-color: rgb(245, 245, 245);
    margin-bottom: 15px;
    padding: 12px;
    // cursor: pointer;
    box-shadow: 0 2px 4px rgb(0 0 0 / 10%);
    border-radius: 8px;
    transition: all 0.3s ease;

    &:hover {
      box-shadow: 2px 2px 2px 0px rgb(255 255 255 / 50%),
        7px 7px 20px 0px rgb(0 0 0 / 10%), 4px 4px 5px 0px rgb(0 0 0 / 10%);
    }

    // &:not(:last-child) {
    //   margin-bottom: 15px;
    // }

    &-top {
      display: grid;
      grid-template-columns: 200px 1fr;
      column-gap: 20px;
      margin-bottom: 20px;
      font-size: 14px;

      .cover {
        width: 200px;
        border-radius: 4px;
      }
    }

    &-title {
      font-size: 22px;
      font-weight: bold;
      margin-bottom: 10px;
    }

    &-desc {
      display: -webkit-box;
      font-size: 12px;
      line-height: 1.5;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 5;
      overflow: hidden; /*超出部分隐藏*/
      text-overflow: ellipsis; /*省略号展示*/
      overflow-wrap: break-word;
    }

    &-bottom {
      font-size: 12px;
      font-weight: 300;

      span:not(:first-child) {
        margin-left: 5px;
      }
    }
  }
</style>
