<template>
  <div class="container mt-5">
    <h1>Blog</h1>
    <div class="row">


       <div
       v-for="(item, index) in articles" :key="index"
       class="col-md-3">
         <h2>
            <nuxt-link :to="`/blog/${item.id}`">{{item.title}}</nuxt-link>
         </h2>
       </div>

    </div>

  </div>
</template>

<script>


export default {
  data(){
    return{
      articles: [
        {id:1,title:'Articulo 1',description:'ADas asdasd asdasdasd'},
        {id:2,title:'Articulo 2',description:'ADas asdasd asdasdasd'},
        {id:3,title:'Articulo 3',description:'ADas asdasd asdasdasd'},
        {id:4,title:'Articulo 4',description:'ADas asdasd asdasdasd'}
      ]
    }
  },
  components: {

  }
}
</script>
