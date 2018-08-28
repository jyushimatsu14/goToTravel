<template>
  <div id="app">
    <!-- 显示的是当前路由地址所对对应的内容 -->
    <keep-alive>
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
