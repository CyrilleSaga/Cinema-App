<template lang="html">
    <div class="movies_content">
        <div class="movie_item" v-for="item in movies" :key="item.id">
            <div class="movie_photo">
                <img :src="'https://image.tmdb.org/t/p/w500' + item.poster_path" alt="">
            </div>
            <div class="movie_item_footer">
                <h3>{{ item.name }}</h3>

            </div>
        </div>
    </div>
</template>

<script>

const API_MOVIES_LINK = "http://api.themoviedb.org/3/tv/popular?api_key=ca04d10155ed8e2a32b744de9481045e"

export default {
    name: "MoviesList",
    data() {
        return {
            movies: []
        }
    },
    beforeMount() {
        this.getMovies()
    },
    methods: {
        async getMovies() {
            const request = new Request( API_MOVIES_LINK
                , {
                    method: "get",
                    mode: "cors",
                    cache: "default",
                }
            );
            const res =     await fetch(request);
            const data = await res.json();
            this.movies = data.results;
        }
    }
}
</script>

<style lang="scss" scoped>
    .movies_content {
        width: 85%;
        background-color: #21252B;
        margin-right: 1%;

        .movie_item {
            width: 18%;
            margin: 1%;
            text-align: center;
            border-radius: 10px;
            display: inline-block;
            box-shadow: 1px 1px 20px rgba(255, 255, 255, 0.1);
            transition: 1s;

            .movie_photo {
                img {
                    width: 100%;
                    border-top-left-radius: 10px;
                    border-top-right-radius: 10px;
                }
            }

            &:hover {
                transition: 1s;
                box-shadow: 1px 1px 20px rgba(0, 0, 0, 0);
                cursor: pointer;
            }
        }

    }
</style>
