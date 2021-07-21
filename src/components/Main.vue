<template>
<div class="container-full cont-main">
  <div class="row">
    <h1>ORIGINALI NETFLIX</h1>
    <Movie
      class="col-3"  v-for="(item,index) in albumsMovie" 
      :key='index'
      :img='item.poster_path'
      :title='item.title'
      :title_original='item.original_title'
      :original_language="item.original_language"
      :vote_average='item.vote_average'
    />
  </div>
</div>
 
</template>

<script>
import Movie from './Movie.vue'
export default {
  name: 'Main',
  components:{
     Movie,
  },
  props: {
      albumsMovie: Array,
  },

};
</script>

<style lang="scss" scoped>
.cont-main{
  background-color: rgba(0, 0, 0, 0.521);
  h1{
    color: white;
    font-size: 24px;
    margin: 10px;
  }
}
</style>