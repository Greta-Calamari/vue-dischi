<template>
<div class="container main">
    <SearchMenu @mySearch="setSearchText" :MusicGeneres="genre"/>
    <div class="row">

    <div class="col-6 col-md-4 col-lg-2 gy-5" v-for="(disk,index) in filteredMenu" :key="index">
        <AppCard :item ="disk"/>
    </div>
    </div>



</div>
    
</template>

<script>
import axios from "axios";
import AppCard from './AppCard.vue'
import SearchMenu from './SearchMenu.vue'


export default {
    name:"AppMain",
    components:{
        AppCard,
        SearchMenu,
    },
    data(){
        return{
            diskList:[],
            genre:[],
            searchText:'',
            adiPath:'https:flynn.boolean.careers/exercises/api/',
            // loading:false,
        }



    },mounted(){
        // this.loading = true;
        axios.get(this.adiPath + 'array/music').then((res)=>{
            console.log(res.data.response)
            this.diskList = res.data.response
            this.diskList.forEach((el)=>{
                if(!this.genre.includes(el.genre)){
                    this.genre.push(el.genre)

                }

            })
            // this.loading = false;

        }).catch((error)=>{
            console.log(error)
            // this.loading = false;
           
        })


    },methods:{
        setSearchText(txt){
            this.searchText = txt;
            console.log('setSearchText',txt)

        }
    },computed:{
        filteredMenu(){
            if(this.searchText === ""){
            return this.diskList;
        }
        return this.diskList.filter((item)=>{
            return item.genre === this.searchText;
        })
        }

    },
    
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