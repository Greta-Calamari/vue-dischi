<template>
    <div>
        <select name="" id="" v-model="inputText" @click="search">
            <option value="">All</option>
            <option :value="genre" v-for="genre in MusicGeneres" :key="genre">{{genre}}</option>

        </select>

    </div>
</template>
<script>
export default {
    name:'SearchMenu',
    data(){
        return{
            inputText:'',

        }
    },props:['MusicGeneres'],
    methods:{
        search(){
            this.$emit('mySearch',this.inputText);
            this.inputText='';


        },

    }
    
}
</script>

<style lang="scss" scoped>

</style>