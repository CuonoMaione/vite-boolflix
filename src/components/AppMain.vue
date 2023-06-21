<template lang="">
   <ul>
    <li v-for="title in titleList">{{ title.original_title}}</li>
   </ul>
</template>
<script>
import axios from 'axios';

export default {
    name: 'AppMain',
    titleList : [],

    data() {
        return {
            apiUrl : 'https://api.themoviedb.org/3/discover/movie?api_key=5c7e4b34b42dc8001eec6169d917c0ca',
        }
    },  

    created() {
        axios.get(this.apiUrl)
        .then((response) => {
            this.titleList = response.data.results
            console.log(this.titleList)
        })
    },

}
</script>
<style lang="scss" scoped>
    
</style>
