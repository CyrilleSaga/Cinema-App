<template>
    <div id="app">
        <HomeView />
    </div>
</template>

<script>
    import HomeView from './components/HomeView.vue'
    export default {
        components: {
            HomeView
        }
    }
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: white;
}
</style>
