
<template>
<adminmenu/>
<div class="container">
    <div class="row">
        {{getArt}}
        <div v-for="item in getArt" :key="item.id"  class="card">
        <h5 class="card-header">{{item.heading}}</h5>
        <div class="card-body">
            <p class="card-text">{{item.description}}</p>
            {{item.id}}
                <div class="col-2 align-self-start">
                <router-link  class="btn btn-primary"  :to="{ name: 'editArticle', params:{id: item.id}}">Редактировать... </router-link>
                </div>    
                    <div class="col-2 align-self-end">
                    <button v-on:click = "deleteItem"  class="btn btn-danger"  >Удалить...{{item.id}} </button>
                    </div>
            </div>
        </div>
    </div>
</div>

</template>

<script>
import adminmenu from '@/components/newsmenu.vue'
export default{
    name: 'indexAdmin',
    components:{
        adminmenu
    },
    computed:{
        getArt(){
            return this.$store.getters.getArticle
        }
    },
    methods:{
        deleteItem(id){
            alert("TEST" + id)
        }
    }
}
</script>

<style scoped>
.card{
    border-color:blue;
    padding-left:0px;
    padding-right:0px;
}
</style>
