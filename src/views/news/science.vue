<template>
<newsmenu />
Наука
{{getArt}}
</template>
<script>
import newsmenu from '@/components/newsmenu.vue'
export default{
    name: 'science',
    components:{
        newsmenu
    },
     computed:{
        getArt(){
            return this.$store.getters.getArticleSort(5)
        }
    }
}
</script>