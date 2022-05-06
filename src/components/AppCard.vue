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
<style lang="scss" scoped>
@import "../assets/style/vars.scss";

h4{
    text-transform:uppercase;
    
}
img{
    color: $text-color;
    box-shadow: 0 0 6px 3px rgba(#000, 0.15);
    width: 100%;

}

</style>