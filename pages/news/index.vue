<template lang="pug">
    .news
        .title News Index Page
        p {{$route.params.newsId}}
        nuxt-link(to="/") 首页
        // 如果没有其他参数可直接用path
        nuxt-link(to="/news/123") news-1
        // 参数不通过校验会跳转到error页面
        nuxt-link(to="/news/456") news-2
        // 使用传参形式
        nuxt-link(:to="{name:'news-id', params: {id: 678, type: '科技新闻', title: '科技改变未来'}}") news-3
        .list(v-for="item in newsList")
            nuxt-link(:to="`/news/${item.id}`") {{item.name}}
</template>

<script>
import axios from 'axios'
export default {
    transition: 'news',
    data() {
        return {}
    },
    asyncData({params}) {
        return axios.get('http://yapi.fpi-inc.site/mock/313/map/incident/mock/news-lists').then(res => {
            return {
                newsList: res.data
            }
        })
    },
    mounted() {
        console.log(this.newsList)
    }
}
</script>

<style lang="stylus">
.news
    display flex
    flex-direction column
</style>