<template lang="html">
    <div class="side_bar">
        <h3>Genre Film</h3>
        <div class="side_bar_body">
            <li v-for="item in genres" :key="item.id">
                {{ item.name }}
            </li>
        </div>
    </div>
</template>

<script>

const API_GENRE_LINK = "https://api.themoviedb.org/3/genre/movie/list?api_key=ca04d10155ed8e2a32b744de9481045e"

export default {
    name: "SideBar",
    data() {
        return {
            genres: []
        }
    },
    beforeMount() {
        this.getGenre()
    },
    methods: {
        async getGenre() {
            const request = new Request( API_GENRE_LINK
                , {
                    method: "get",
                    mode: "cors",
                    cache: "default",
                }
            );
            const res =     await fetch(request);
            const data = await res.json();
            this.genres = data.genres;
        }
    }
}
</script>

<style lang="scss" scoped>
.side_bar {
    background-color: #21252B;
    width: 15%;
    margin: 0 1%;
    padding: 1% 1.5%;

    h3 {
        text-align: center;
        font-size: 27px;
        color: #de3c31;
    }

    .side_bar_body {
        list-style-type: none;
        margin-bottom: 1.5em;

        li {
            line-height: 30px;
            cursor: pointer;

            &:hover {
                color: #de3c31;
                opacity: 0.7;
            }
        }
    }

}
</style>
