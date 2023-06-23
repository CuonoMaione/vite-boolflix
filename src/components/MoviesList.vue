<template>
      <div class="container">
        <div class="row">
            <ul class="col-3 mb-5 list-group-numbered" v-for = "title in titleList">
                <img src="" alt="">
                <li> {{ title.title }}</li>
                <li>{{ title.original_title }}</li>
<!-- "getImagePath(`'../assets/img/' + '${title.original_language}' + 'png'`)" -->
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
        titleList : Array,
    },
    data() {
        return {
            nationsList:['it','en','ja','de','es','fr'],
        }
    },
    methods:{
       getImagePath : function (imgPath) {
            return new URL(imgPath, import.meta.url).href;
    
    }
    }
}
</script>
<style lang="scss" >
    img{
        width: 40px;
    }
</style>