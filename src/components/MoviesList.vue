<template>
      <div class="container">
        <div class="row">
            <ul class="col-3 mb-5 list-group-numbered" v-for = "title in titleList">
                <li> {{ title.title }}</li>
                <li>{{ title.original_title }}</li>
                <li>{{ title.original_language }}</li>
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
    }
}
</script>
<style lang="scoped">
    
</style>