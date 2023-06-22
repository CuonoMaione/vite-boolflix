<template lang="">
    <div class="container">
        <div class="row justify-content-between align-content-center">
            <div class="col-5">
               <input type="text" v-model=" searchedMovies" @keyup.enter="$emit('searched',searchedMovies)" >
            </div> 
            <div class="col-7">
                <h1>{{ searchedMovies }}</h1>
            </div>
            
        </div>
    </div> 
</template>
<script>
export default {
    name: 'SearchBar',
    props : {
        
    },
    data() {
        return {
            searchedMovies : "",
        }
    },
}
</script>
<style lang="scoped">
    
</style>