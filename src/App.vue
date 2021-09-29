<template>
    <div id="main">
        <NavBar />
        <router-view></router-view>
        <MainFooter />
    </div>
</template>

<style lang="scss">
html,
body {
    height: 100%;
}
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    min-height: 100vh;
}

#main {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
</style>

<script>
import NavBar from "@/components/Navigation/NavBar";
import MainFooter from "@/components/Navigation/MainFooter";
export default {
    components: {
        NavBar,
        MainFooter,
    },
};
</script>
