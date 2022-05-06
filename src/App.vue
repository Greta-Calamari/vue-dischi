<template>
  <div id="app">
    <header>
    <AppHeader/>
    </header>
    <main>
      <AppMain/>
    </main>

  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'




export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain,
    
    
  }
}
</script>

<style lang="scss">
@import "@/assets/style/general.scss";
main{
  background-color: $background;
  height: 100vh;
  
}
  


</style>
