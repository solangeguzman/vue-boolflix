<template>
 <div>
   <!-- <img :src=""/> -->
   <div>{{ title }}</div>  
   <div>{{ original_title }}</div>
   <span>{{ vote_average }}</span>   
 </div>
</template>

<script>
export default {
  name: 'Movie',
  props:{
      title: String,
      original_title: String,
      orignal_language: String,
      vote_average: String
  },
};
</script>

<style lang="scss" scoped>
</style>