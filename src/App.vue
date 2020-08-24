<template>
  <div id="app">
    <!-- 显示当前路由对应组件 -->
    <keep-alive exclude="Detail">   <!-- 除detail组件不缓存 -->
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
