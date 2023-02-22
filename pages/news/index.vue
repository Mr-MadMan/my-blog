<template>
  <div class="wrapper">
    <li v-for="(item, index) in newsList" :key="index" @click="gotoDetail(item)">{{item.title}}</li>
  </div>
</template>

<script>
  export default {
    name: '',
    data(){
      return {
        newsList: [
          {id: 1, title: '五芳斋倒闭'},
          {id: 2, title: 'metro dropped the album'},
        ]
      }
    },
    created(){},
    methods:{
      gotoDetail(item) {
        this.$router.push({name: 'news-id', params: item})
      }
    }
  }
</script>
<style scoped lang="scss">
</style>
