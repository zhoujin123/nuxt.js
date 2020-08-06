<template lang="pug">
    .about
        .title About Index Page
        .aboutid {{$route.params.aboutId}}
        nuxt-link(to="/") HOME
</template>