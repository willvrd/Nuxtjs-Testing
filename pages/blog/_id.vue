<template>
  <div class="container mt-5">

    <h1>Blog</h1>
    <h2>Articulo id: {{$route.params.id}}</h2>

    <div class="card">
      <div class="card-body">
        <h3>{{article.title}}</h3>
        <p class='small'>
          {{article.nameAuthor}}
        </p>
        <p>{{article.body}}</p>
        <nuxt-link to="/blog" class="btn btn-primary">Back</nuxt-link>
      </div>

    </div>

  </div>
</template>

<script>

import axios from 'axios';

export default {
  components: {

  },
  data(){
    return{
      //article: '' Deleted 'cause bug to paint screen
    }
  },

  /*
  async created(){

    try {

      const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`);
      this.article = res.data;

      const resAuthor = await axios.get(`https://jsonplaceholder.typicode.com/users/${res.data.userId}`);

      // Magic :)
      this.article.nameAuthor = resAuthor.data.name;

      //That is a problem, because don't show the author

    } catch (error) {
      console.log(error);
    }

  },
  */

  /**
   * https://nuxtjs.org/guide/async-data
   * Here 'this' don't work
   */
  async asyncData({isDev, route, store, env, params, query, req, res, redirect, error}) {

    try {

      const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);

      const article = res.data; // Definir aqui x const

      const resAuthor = await axios.get(`https://jsonplaceholder.typicode.com/users/${res.data.userId}`);

      article.nameAuthor = resAuthor.data.name;

      return {article}; // Required

    } catch (error) {
      console.log(error);
      return {error:error} // Required
    }
  },
}
</script>
