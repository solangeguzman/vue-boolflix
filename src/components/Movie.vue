<template>
  <div class="poster-container">  
       <div class="section-poster">
            <img class="poster" :src="'https://image.tmdb.org/t/p/w300/'+ img"/>
               <!-- info film -->
            <div class="film-info flex">
                <div> {{title}}</div>
                <div>{{original_title}}</div>
                <span>lingua originale:<img class="flag" :src="flag(original_language)"></span>  
                <div class="voto">
                   <i class="fas fa-star" v-for="star in star" :key="star"></i>
                   <i class="far fa-star" v-for="(index) in (5-star)" :key="index"></i>
                </div>
            </div>
                <!-- fine -->
        </div>
  </div>   
</template>

<script>
export default {
  name: 'Movie',
  props:{
      img: String,
      title: String,
      original_title: String,
      original_language: String,
      vote_average: Number,
  },
  computed: {
    star() {
      return Math.floor(this.vote_average / 2);
    },
  },
  methods:{
    flag(original_language){
    return require("../assets/icon/" + original_language + ".png");
    }
  }
  
};
</script>

<style lang="scss" scoped>

.poster-container {
  .section-poster {
    background: rgb(177, 169, 169);
    height: 417px;
    margin: 8px;
    border-radius: 15px;
    .poster{
      border-radius: 15px;
      width: 100%;
    }
      &:hover .film-info {
      display: block;
    }
    .film-info {
      height: 200px;
      font-size: 24px;
      color: rgb(245, 243, 243);
      position: relative;
      bottom: 55%;
      text-align: center;
      background-color: rgb(27, 27, 27, 0.5);
      justify-content: center;
      display: none;
    }
  }
  .voto{
    .fas{color: rgba(235, 216, 108, 0.603);}
    .far{color: rgba(255, 255, 255, 0.664);}
  }

}

</style>