<template>
    <div class="slider">

        <h3 >{{title}}</h3>

        <span @mouseover="scrollLeft" @mouseout="clearScroll" class="handle handlePrev active">
          <i class="fa fa-caret-left" aria-hidden="true"></i>
        </span>

        <div ref="scroller" class="row">
            <div class="row__inner">
                <filme v-for="movie in movies"  :key="movie.id" :name="movie.name" :url="movie.url"></filme>
            </div>
        </div>

        <span @mouseover="scrollRight" @mouseout="clearScroll" class="handle handleNext active">
          <i class="fa fa-caret-right" aria-hidden="true"></i>
        </span>

      </div>
</template>

<script>

    import Filme from './Filme.vue'
    export default {
        name: 'category',
        components:{
            Filme
        },
        props:['title', 'movies'],
        methods:{
            scrollRight: function(){
                this.intervalo = setInterval(() => { this.$refs.scroller.scrollLeft += 1 }  , 5);
            },
            scrollLeft: function(){
                this.intervalo = setInterval(() => { this.$refs.scroller.scrollLeft -= 1 }  , 5);
            },
            clearScroll: function(){
                clearInterval(this.intervalo);
            }
        }
    }
</script>

<style lang="scss">

</style>


