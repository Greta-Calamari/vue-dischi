<template>
<div class="container main">
    <div class="row">

    <div class="col-6 col-md-4 col-lg-2 gy-5" v-for="(disk,index) in diskList" :key="index">
        <AppCard :item ="disk"/>
    </div>
    </div>



</div>
    
</template>

<script>
import axios from "axios";
import AppCard from './AppCard.vue'

export default {
    name:"AppMain",
    components:{
        AppCard,
    },
    data(){
        return{
            diskList:[],
            adiPath:'https:flynn.boolean.careers/exercises/api/',
            // loading:false,
        }


    },mounted(){
        // this.loading = true;
        axios.get(this.adiPath + 'array/music').then((res)=>{
            console.log(res.data.response)
            this.diskList = res.data.response
            // this.loading = false;

        }).catch((error)=>{
            console.log(error)
            // this.loading = false;
           
        })


    }
    
}
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

.main{
    
    background-color: $background;
}

.col-lg-2 {
    flex: 0 0 auto;
    width: 19.666667%;
}







</style>