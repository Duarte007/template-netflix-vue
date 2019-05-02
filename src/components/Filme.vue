<template>
    <div class="d-card" :style="styleCard" @click="openDetail()" @mouseout="closeDetail()">
        <div class="d-card__media">
            <img class="d-card__img" :src="url" alt=""  />
        </div>
        <div class="d-card__details">
            <div class="d-card__title">
                {{name}}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'movie',
        data(){
            return {
                canClose: false,
                styleCard: null
            }
        },
        props:['name', 'url'],
        methods:{
            openDetail: function(){
                this.styleCard = "transform: scale(1.9); margin-right: 110px;"
                this.canClose = true;
            },
            closeDetail: function(){
                if(this.canClose){
                    this.canClose = false;
                    this.styleCard = null;
                }
            }
        }
    }
</script>

<style lang="scss">

</style>


