<template lang="html">
    <nav class="nav_bar">
        <router-link class="logo" :to="{ name: 'home', params: {} }">Watch.Stream</router-link>
        <div class="nav_link">
            <router-link class="nav_link_item" :to="{ name: '', params: {} }">Films</router-link>
            <router-link class="nav_link_item" :to="{ name: '', params: {} }">Séries</router-link>
            <router-link class="nav_link_item" :to="{ name: '', params: {} }">Genre</router-link>
            <router-link class="nav_link_item" :to="{ name: '', params: {} }">Contact</router-link>
            <router-link class="nav_link_item" :to="{ name: '', params: {} }">A Propos</router-link>
        </div>
        <div class="nav_search">
            <font-awesome-icon icon="fa-solid fa-search" />
        </div>
    </nav>
</template>

<script>
export default {
    name: 'NavBar'
}
</script>

<style lang="scss" scoped>
    .nav_bar {
        display: flex;
        padding: 15px 2em;
        background-color: #21252B;
        justify-content: space-between;
        margin-bottom: 1%;

        a.logo {
            color: white;
            font-weight: 900;
            font-size: 2.5em;
            font-style: oblique;
            letter-spacing: 5px;
        }

        .nav_link {
            width: 60%;
            display: flex;
            text-align: center;
            justify-content: space-evenly;

            a.nav_link_item {
                width: 100%;
                color: #d9d9d9;
                font-size: 20px;
                text-align: center;
                padding-top: 1.5%;

                &:hover {
                    font-weight: 600;
                    color: gray;
                    transition: 1s;
                }
            }

        }
    }
</style>
