<template>

   <header>
    <input type="text" placeholder="Search" v-model="searchString" @keyup.enter="$emit('search', searchString)"/>
   </header>

</template>

<script>
export default {
  name: 'Header',
};
</script>

<style lang="scss" scoped>
</style>