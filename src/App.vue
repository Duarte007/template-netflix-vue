<template>
  <div class='contain'>
        <categoria  v-for="category in categories" 
            :key="category.id" 
            :title="category.title"
            :movies="category.movies">
        </categoria>
  </div>
</template>

<script>

  import teste from './components/Teste.vue'
  import categoria from './components/Categoria.vue'

  export default {
    name: 'batata',
    components:{
      teste,
      categoria
    },
    data () {
      return {
        msg: 'Vai começar',
        intervalo: null,
        categories:[]
      }
    },
    created(){
        this.$http.get('http://localhost:3000/categories').then(response=>{
            this.categories = response.body;
        });
    }
  }
</script>

<style lang="scss">
  @import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.css");
  @import './assets/css/styles.css';
</style>
