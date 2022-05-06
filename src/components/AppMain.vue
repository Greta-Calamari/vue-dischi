<template>
<div class="container">
    <div class="col-6 col-md-4 col-lg-3 gy-3" v-for="(disk,index) in diskList" :key="index">
        <AppCard :item="disk"/>
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
            loading:false,
        }


    },mounted(){
        this.loading = true;
        axios.get(this.adiPath + 'array/music').then((res)=>{
            console.log(res.data)
            this.diskList = res.data
            this.loading = false;

        }).catch((error)=>{
            console.log(error)
            this.loading = false;
           
        })


    }
    
}
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

.container{
    height: 100vh;
    background-color: $background;
}




</style>