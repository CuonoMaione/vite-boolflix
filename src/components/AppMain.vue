<template lang="">
    
    <SearchBar  @searched="completeSearch" />
    <MoviesList :movieList="movieList" :tvList="tvList" /> 

</template>
<script>
import axios from 'axios';
import SearchBar from './SearchBar.vue';
import MoviesList from './MoviesList.vue';
export default {
    name: 'AppMain',
    components:{
       SearchBar,
       MoviesList,
    },
    
    

    data() {
        return {
            apiMoviesUrl : 'https://api.themoviedb.org/3/search/movie?api_key=5c7e4b34b42dc8001eec6169d917c0ca&',
            apiTvUrl : 'https://api.themoviedb.org/3/search/tv?api_key=5c7e4b34b42dc8001eec6169d917c0ca',
            titleList : [],
            tvList : [],
            movieList:[],
        }
    },  

    methods: {
        resultMovies(message){
            

            axios.get(this.apiMoviesUrl,{
                params:{
                    query: message
                }
            })
            .then((response) => {
           this.movieList=( response.data.results ) 
            
            })

            
        },
        resultTv(message){
        axios.get(this.apiTvUrl,{
            params:{
                query: message
            }
        })
        .then((response) => {
       this.tvList = (response.data.results) 
       
        })
    },

    completeSearch(message){
        this.resultMovies(message);
        this.resultTv(message);
    }
    }
}
</script>
<style lang="scss" scoped>
    
</style>
