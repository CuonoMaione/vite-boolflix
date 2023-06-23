<template lang="">
    
    <SearchBar  @searched="resultMovies" />
    <MoviesList :titleList="titleList" /> 

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
            this.titleList = response.data.results
            
            })

            axios.get(this.apiMoviesUrl,{
                params:{
                    query: message
                }
            })
            .then((response) => {
            this.titleList = response.data.results
            console.log(response.data.results)
            })

    },

    created() {
      
    },

    }
}
</script>
<style lang="scss" scoped>
    
</style>
