/* 
  路由跳转，通过page目录自动生成路由
  跳转使用nuxt-link  
  name: 路由名称  params: 传参
 */
<template lang="pug">
.page
  ul
    li
      nuxt-link(:to="{name: 'index'}") HOME
    li
      nuxt-link(:to="{name: 'about', params: {aboutId: 13}}") About
    li
      nuxt-link(:to="{name: 'news', params: {newsId: 13}}") News
</template>

<script>
export default {}
</script>

<style>
</style>
