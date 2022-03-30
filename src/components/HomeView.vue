<template lang="html">
    <div>
        <NavBar />
        <div class="content">
            <SideBar />
            <movies-list />
        </div>
    </div>
</template>

<script>
    import NavBar from './NavBar.vue'
    import SideBar from './SideBar.vue'
    import Movies from './Movies.vue'
    export default {
        components: {
            NavBar, SideBar, "movies-list" : Movies
        }
    }
</script>

<style lang="scss" scoped>
    .content {
        display: flex;
        justify-content: space-evenly;
    }
</style>
