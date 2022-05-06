<template>
<!-- author: "Bon Jovi"
genre: "Rock"
poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
title: "New Jersey"
year: "1988" -->
    <div class="card my-5 text-center">
        <img :src="item.poster" alt="">
        <h4>{{item.title}}</h4>
        <div class="sub">{{item.author}}</div>
        <div class="sub">{{item.year}}</div>
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

.card{
    height: 400px;
    background-color: $bg-color;
    .sub{
    color: $text-color;
    }
}
    



h4{
    text-transform:uppercase;
    color: $text-color;
    
}
img{
    
    width: 80%;
    margin: 5% auto;

}

</style>