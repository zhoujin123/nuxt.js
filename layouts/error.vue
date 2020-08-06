<template lang="pug">
    .container
        img(src="~/assets/img/404.svg")
        .line(v-if="error.statusCode === 404") 您的页面走丢了~
        .line(v-else) 您访问的页面发生应用错误异常
        nuxt-link.line(to="/") 请点击返回首页
</template>

<script>
export default {
    props: ['error'],
    // layout: 'blog'
}
</script>

<style lang="stylus">
.container
    display flex
    flex-direction column
    align-content center
    align-items center
    justify-content center
    img
        width 200px
    .line
        margin-top 30px
</style>