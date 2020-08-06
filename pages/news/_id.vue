<template lang="pug">
    .news-content
        p NEWS CONTENT
        p {{$route.params.id}}
        p {{$route.params.type}}
        nuxt-link(:to="{name: 'news'}") 返回上一级
</template>

<script>
export default {
    validate({params}){
        return /^\d+$/.test(params.id)
    },
    data() {
        return {
            title: this.$route.params.title,
        }
    },
    head() {
        return {
            title: this.title,
            meta:[
                {hid: 'description', name: 'news3', content: 'This is news page'}
            ],
        }
    }
}
</script>