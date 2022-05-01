<template>
<newsmenu />
Экономика
{{getArt}}
</template>
<script>
import newsmenu from '@/components/newsmenu.vue'
export default{
    name: 'economics',
    components:{
        newsmenu
    },
     computed:{
        getArt(){
            return this.$store.getters.getArticle
        }
    }
}
</script>