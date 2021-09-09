<template>
    <NavBar/>
    <router-view></router-view>
    <MainFooter/>
</template>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
</style>

<script>
import NavBar from '@/components/Navigation/NavBar'
import MainFooter from '@/components/Navigation/MainFooter'
export default {
  
  components:{
    NavBar,
    MainFooter
  }
}
</script>
