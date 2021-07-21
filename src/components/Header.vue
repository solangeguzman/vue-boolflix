<template>

   <header >
     <div class="container-full">
       <div class="row">
         <div class="col">
           <nav class="lista">
             <span><img src="../assets/netflix.jpg" width="100" alt="logonetflix"></span> 
             <span class="li-lista"><a style="color:white" href="#">Home</a></span>
             <span class="li-lista"><a style="color:white" href="#">Serie TV</a></span>
             <span class="li-lista"><a style="color:white" href="#">Film</a></span>
             <span class="li-lista"><a style="color:white" href="#">Originali</a></span>
             <span class="li-lista"><a style="color:white" href="#">Aggiungi di recente</a></span>
             <span class="li-lista"><a style="color:white" href="#">La mia lista</a></span>
             <span>
              <span>
                <!-- -----barra ricerca -->
                  <span class="ricerca">
                    <input id="input" type="text" placeholder="Search" v-model="searchString" @keyup.enter="$emit('search', searchString)"/>
                     <button @click="$emit('search', searchString)"><i class="fas fa-search"></i></button>
                  </span>
                <!-- ---------- -->
                  
                  <span id="margin" class="fin-list">Bambini</span>
                  <span class="fin-list"><a style="color:white" href="#"></a><i id="margin" class="fas fa-bell"></i></span>
                  <span class="fin-list"><i  id="margin" class="fas fa-sort-down"></i></span>
              </span>   
             </span>
           </nav>
        </div>
          
       </div>
       
     </div>
     
   </header>

</template>

<script>
export default {
  name: 'Header',
  data () {
    return{
      searchString: '',
    }
  }
};
</script>

<style lang="scss" scoped>
nav{
  background-color: black;
  display: flex;
  
  .lista{
    justify-content: space-around;
    color: rgba(255, 255, 255, 0.699);
  }
  .li-lista{
       margin-top: 20px;
       margin-left: 10px;
    a { 
    text-decoration: none;
    } 
  }
  .ricerca{
    margin-left: 300px;
    color: white;
  }
  .fin-list{
    margin-top: 20px;
    margin-left: 11px;
    color: white;
  }
  #margin{
    margin-top: 20px;
  }
  #input{
    border-radius: 15px;
    border: rgb(77, 74, 74) 1px solid;
    padding: 4px;
   
  }
  button{
    border-radius: 15px;
    border: black solid 1px;
    background-color: black;
    i{
      color: white;
    }
  }
  
}
</style>