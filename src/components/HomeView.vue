<template lang="html">
    <div>
        <NavBar />
        <SideBar />
    </div>
</template>

<script>
    import NavBar from './NavBar.vue'
    import SideBar from './SideBar.vue'
    export default {
        components: {
            NavBar,
            SideBar
        }
    }
</script>

<style lang="scss" scoped>
</style>
