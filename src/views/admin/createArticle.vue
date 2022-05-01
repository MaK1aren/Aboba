<template>
<adminmenu/>
<form class="row g-3">
  <div class="col-md-6">
    <label for="Heading" class="form-label">Заголовок</label>
    <input v-model='article.heading' type="text" class="form-control" id="Heading">
  </div>
  <div class="col-md-6">
    <label for="Author" class="form-label">Автор</label>
    <input v-model='article.author' type="text" class="form-control" id="Author">
  </div>
  <div class="col-md-6">
    <label for="Description" class="form-label">Краткое описание</label>
    <input v-model='article.decription' type="text" class="form-control" id="Decription">
  </div>
  <div class="col-md-4">
    <label for="Category" class="form-label">Категория</label>
    <select v-model='article.category' id="CAtegory" class="form-select">
      <option selected>Выберите категорию...</option>
      <option>Политика</option>
      <option>Экономика</option>
      <option>Общество</option>
      <option>Проишествия</option>
      <option>Наука</option>
      <option>Спорт</option>
    </select>
  </div>
  <div class="col-md-2">
    <label for="articleData" class="form-label">Дата публикации</label>
    <input v-model='article.dateArticle' type="date" class="form-control" id="articleData">
  </div>
  <div class="col-12">
    <label for="content" class="form-label">Контент</label>
    <textarea v-model='article.content' type="text" class="form-control" id="content" ></textarea>
  </div>
  <div class="col-12">
    <button v-on:click="addArticle" class="btn btn-primary">Сохраниь</button>
  </div>
</form>
</template>

<script>
import adminmenu from '@/components/adminmenu'
export default {
    name: 'createArticle',
    components:{
        adminmenu
    },
    data(){
        return{
        article:{
            id:Date(),
            heading: '',
            content: '',
            author: '',
            category: '',
            decription: '',
            dateArticle: ''
            }
        }
    },
        methods:{
            addArticle(){
                this.$store.commit('addArt', this.article)
        }
    }
}

</script>



<style scoped>
#content{
    height: 300px;
} 
</style>
