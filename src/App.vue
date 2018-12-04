<template>
  <div id="app">
    <!--显示当前路由组件-->
    <router-view/>  <!--路由组件-->
    <!--普通组件-->
    <FooterGuide v-show="$route.meta.FooterGuide"/>    <!--标识底部显示-->
  </div>
</template>

<script>
  import FooterGuide from './components/FooterGuide/FooterGuide'

  export default {
     mounted() {
    //异步获取地址数据(到vuex的state中)
      this.$store.dispatch('getAddress')
      //异步获取取商铺列表
      this.$store.dispatch('getShops')
      //异步获取当前用户信息
      this.$store.dispatch('getUser')
    },
    name: 'App',
    components: {
      FooterGuide,
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>


</style>
