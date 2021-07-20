<template>
 <div>

    <img  id="hover.img" :src="'https://image.tmdb.org/t/p/w200/'+ img"/>
  
   <!-- <div> {{poster_path}} </div> -->
     <br>
    <div class="info-films">
      <h1> {{title}}-{{name}}</h1>
      <!-- ----- -->
      <div>
          <span>{{ original_title }}</span>
      </div>
      <!-- ------- -->
      <div>original language: {{original_language}} </div>
      <div>
          <img class="flag" :src="returnflag(original_language)" alt="flag">
      </div>
      
      <!-- <span>{{ vote_average }}</span>  -->
     
      <div>
       <span>
         <ul v-if="vote > 0">
          <li><i class="far fa-star"></i></li>
          <li v-if="vote > 1"><i class="far fa-star"></i></li>
          <li v-if="vote > 2"><i class="far fa-star"></i></li>
          <li v-if="vote > 3"><i class="far fa-star"></i></li>
          <li v-if="vote > 4"><i class="far fa-star"></i></li>
         </ul>
      </span>
    </div>
 </div>
</template>

<script>
export default {
  name: 'Movie',
  props:{
      // img: String,
      title: String,
      original_title: String,
      orignal_language: String,
      vote_average: String
  },
  data() {
    return {
      vote: Math.round(this.vote_average / 2),
    };
  },
  flag(original_language){
    return require("../assets/" + original_language + ".png");
  }
};
</script>

<style lang="scss" scoped>
.cont-movie{
    
  .info-films {
    text-transform: capitalize;
    position: absolute;
    top: 30%;
    left: 20px;
    z-index: 1002;
    color: white;
    display: none;
  }
}
</style>