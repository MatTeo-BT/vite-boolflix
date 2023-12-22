<template lang="">
    <div>
        <AppSearchVue @search="getMovies"/>
        <AppMain :movies="moviesList"/>
    </div>
</template>
<script>
import AppSearchVue from './components/AppSearch.vue';
import AppMain from './components/AppMain.vue';
import axios from "axios";

export default {
    components: {
        AppSearchVue,
        AppMain
    },
    data() {
        return {
            moviesList: [],
            tvSeriesList: []
        }
    },
    methods: {
        getMovies(searchMovie = ``) {
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=dadc09536eef8ff2ae053c9ebd6144cb&query=' + searchMovie)
                .then((response) => {
                    // handle success
                    console.log(response);
                    this.moviesList = response.data.results;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });

        },
        getTvSeries(searchTvSeries = ``) {
            axios.get('https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=' + searchTvSeries)
                .then((response) => {
                    // handle success
                    console.log(response);
                    this.tvSeriesList = response.data.results;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });

        }
    },

    created() {
        this.getMovies(),
            this.getTvSeries();
    }
}
</script>
<style lang=""> 
</style>