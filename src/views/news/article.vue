
<template>
<div class="container">
    <div class="row">
        <h1> {{Art.heading}} </h1>

        <p> {{Art.content}} </p>

            <p> {{Art.author}} </p>
            <div>{{Art.dateArticle}}</div>
    </div>
</div>

</template>
<script>
export default {
    name: 'artcile',
    data(){
        return{
            article:''
        }
    },
    props:['id'],
    computed:{
        Art(){
            //console.log(this.$store.getters.getArticleItem(this.id))
            return this.$store.getters.getArticleItem(this.id)
        }
    }
    
}
</script>



