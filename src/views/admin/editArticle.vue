<template>
<div class="container">
 <adminmenu/>
  <form class="row g-3">
    <div class="col-md-6">
      <label for="Heading" class="form-label">Заголовк</label>
      <input v-model="artcile.heading"   type="text" class="form-control" id="Heading">
    </div>
    <div class="col-md-6">
      <label for="ArticleAutor" class="form-label">Автор</label>
      <input v-model="artcile.autor" type="text" class="form-control" id="ArticleAutor">
    </div>
      <div class="col-md-6">
        <label for="escpition" class="form-label">Краткое описание</label>
        <textarea v-model="artcile.description" type="text" class="form-control" id="description"></textarea>
      </div>
            <div class="col-md-4">
              <label for="category" class="form-label">Категория</label>
              <select v-model="artcile.category" id="category" class="form-select">
                <option value ="0" selected>Выберите категорию...</option>
                <option value = "1" >Политика</option>
                <option value = "2">Экономика</option>
                <option value = "3">Общество</option>
                <option value = "4">Проишествия</option>
                <option value = "5">Наука</option>
                <option value = "6">Спорт</option>
              </select>
            </div>
    <div class="col-md-2">
      <label for="arcticleDate" class="form-label">Дата публикации</label>
      <input v-model="artcile.dateArticle" type="date" class="form-control" id="arcticleDate">
    </div>
    <div class="col-12">
      <label for="content" class="form-label">Контент</label>
      <textarea v-model="artcile.content" type="text" class="form-control" id="content" ></textarea>
    </div>
    <div class="col-12">
      <button v-on:click="sArticle" class="btn btn-primary">Сохранить</button>
    </div>
  </form>

</div>
</template>

<script>
import adminmenu from '@/components/adminmenu'
export default {
    name: 'editarticle',
    components:{
        adminmenu
    },
    props:['id'],
    data(){
        return{
            artcile:{
               id: '',
               heading: '',
               content: '',
               autor: '',
               category: '',
               description: '',
               dateArticle: ' '
            }
        }
    },
    methods:{
        sArticle(){
                this.$store.commit('saveArticle', this.artcile)
                this.$router.push('/')
        }
    },
    mounted(){
     // this.artcile.id = new Date().getTime()
      this.artcile = this.$store.getters.getArticleItem(this.id)
    }
}
</script>

<style scoped>
#content{
    height: 300px;
}
</style>