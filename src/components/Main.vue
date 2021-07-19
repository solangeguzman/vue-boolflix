<template>
 <div class="row cont-main">
   <nav>
  
  </nav>
    <Movie
      class="col-3"  v-for="Movie in albumsMovie" 
      :key='Movie.id'
      :title='Movie.title'
      :original_title='Movie.original_title'
      :original_language="Movie.original_language"
      :vote_average='Movie.vote_average'
    />
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
//   data () {
//     return{
//       searchString: ''
//     }
//   }
};
</script>

<style lang="scss" scoped>

</style>