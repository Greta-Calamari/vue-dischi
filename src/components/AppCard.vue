<template>
<!-- author: "Bon Jovi"
genre: "Rock"
poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
title: "New Jersey"
year: "1988" -->
    <div class="card">
        <img :src="item.poster" alt="">
        <h4>{{item.title}}</h4>
        <div>{{item.author}}</div>
        <div>{{item.year}}</div>
    </div>

</template>
<script>
export default {
    name:'AppCard',
    props:{
        item:Object,
    }
    
}
</script>
<style lang="sass" scoped>

</style>