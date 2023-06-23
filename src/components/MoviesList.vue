<template>
      <div class="container">
        <div class="row">
            <ul class="col-3 mb-5 list-group-numbered" v-for = "title in completeList">
                <img src="" alt="">
                <li> {{ title.title ? title.title : title.name }}</li>
                <li>{{ title.original_title ? title.original_title : title.original_name }}</li>
                <li>
               <img  v-if="nationsList.includes(`${title.original_language}`)" :src="getImagePath(`../assets/img/` + `${title.original_language}` + `.png`)"> 
               <p v-else>{{ title.original_language }}</p>
                </li>
                
                
                <li>{{ title.vote_average }}</li>

            </ul>    
        </div>
    </div>
</template>
<script>

export default {
    name:'MoviesList',
    props :{
        movieList : Array,
        tvList : Array,
    },
    data() {
        return {
            nationsList:['it','en','ja','de','es','fr'],
            completeList: this.movieList.concat(this.tvList)
        }
    },
    methods:{
       getImagePath : function (imgPath) {
            return new URL(imgPath, import.meta.url).href;
    },
    },

    created(){
        
    },
    
}
</script>
<style lang="scss" >
    img{
        width: 40px;
    }
</style>