<template>
  <div class="layout">
    <header class="header">头部</header>
    <nuxt />
    <footer>底部</footer>
  </div>
</template>

<script>
  export default {
    name: '',
    components:{},
    props:{},
    data(){
      return {

      }
    },
    created(){},
    methods:{}
  }
</script>
<style scoped lang="scss">
  .header {
    padding: 20px 0;
    background-color: blueviolet;
    color: #fff;
  }

  footer {
    background-color: rgb(27, 27, 27);
    color: #fff;
  }
</style>
