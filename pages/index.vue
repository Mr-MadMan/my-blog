<template>
  <div class="container">
    <!-- <div class="blog-content lg:grid md:flex flex-col"> -->
    <div class="blog-content grid">
      <div class="left">
        <template v-for="(item, idx) in acList">
          <post-item :key="`post-item_${idx}`" :ac-data="item" />
        </template>
      </div>
      <div class="right">
        <strong class="text-gray-600">文章分类</strong>
        <ul class="category">
          <li class="category-item">css</li>
          <li class="category-item">vue</li>
          <li class="category-item">typescript</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  layout: 'base',
  data() {
    return {
      acList: [
        {
          id: 1,
          title: 'Nuxt安装使用介绍',
          desc: '貌似从前几年，前后端分离逐渐就开始流行起来，把一些渲染计算的工作抛向前端以便减轻服务端的压力，但为啥现在又开始流行在服务端渲染了呢？如vue全家桶或者react全家桶，都推荐通过服务端渲染来实现路由。搞得我们慌得不行，不禁让我想起一句话：从来没有任何一门语言的技术栈像Javascript一样，学习者拼尽全力也不让精通。没办法，流行，咱们就得学！',
          author: 'madman',
          likes: 23,
          readCount: 32,
          commentCount: 123,
          date: '2023-03-23'
        },
        {
          id: 2,
          title: 'Flex布局详解',
          desc: '布局的传统解决方案，基于盒状模型，依赖 display 属性 + position属性 + float属性。它对于那些特殊布局非常不方便，比如，垂直居中就不容易实现。弹性布局的诞生...',
          author: 'madman',
          likes: 2,
          readCount: 315,
          commentCount: 123,
          date: '2023-03-22'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    max-width: 1000px;
    margin: 20px auto 0;
  }

  .blog-content {
    // display: grid;
    grid-template-columns: 70% 1fr;
    column-gap: 40px;
  }

  .left {
    min-width: 500px;
  }

  .right {
    margin: 0 0 15px;
    padding: 20px 25px;
    background-color: #fff;
    box-shadow: 0 2px 4px rgb(0 0 0 / 10%);
    border-radius: 5px;

    > strong {
      display: block;
      margin-bottom: 10px;
    }

    .category {
      padding: 0;

      &-item {
        list-style: none;
        font-weight: 300;
        line-height: 28px;
        cursor: pointer;

        &:hover {
          color: #3a76cf;
        }
      }
    }
  }
</style>
