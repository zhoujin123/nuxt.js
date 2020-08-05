<template lang="pug">
    .container
        .not-found(v-if="error.statusCode === 404") 页面不存在
        .abnormal(v-else) 应用发生错误异常
        nuxt-link(to="/") 首页
</template>

<script>
export default {
    props: ['error'],
    // layout: 'blog'
}
</script>