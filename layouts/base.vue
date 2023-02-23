<template>
  <div class="base-layout">
    <header>
      <!-- logo slot -->
      <span>Lorclub</span>
      <div class="header-right">
        <nuxt-link to="/about">关于</nuxt-link>
        <nuxt-link to="/">我的</nuxt-link>
      </div>
    </header>
    <main>
      <nuxt />
    </main>
    <footer>
      <p>
        © {{ year }} Lorclub.
        All Rights Reserved. | Thanks all the people who supported me at the darkness.
      </p>
      contact me => email mr_savage21@163.com
    </footer>
  </div>
</template>

<script>
export default {
  name: 'BaseLayout',
  components: {},
  data() {
    return {
      year: new Date().getFullYear()
    }
  },
  created() {},
  methods: {}
}
</script>

<style scoped lang="scss">
  .base-layout {
    display: flex;
    flex-direction: column;
    height: 100%;
  }

  header {
    display: flex;
    justify-content: space-between;
    padding: 10px 20px;
    background-color: rgba(40, 42, 44, 0.6);
    color: #fff;
    font-size: 14px;
  }

  main {
    // flex: 1;
    background-color: #eee;
    min-height: 600px;
  }

  footer {
    padding: 30px 0;
    background-color: #363b3f;
    font-size: 14px;
    color: #fff;
    text-align: center;

    line-height: 1.8;
  }
</style>
