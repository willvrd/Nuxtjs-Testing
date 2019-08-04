<template>
  <div class="container mt-5">

    <h1 class="mb-3">Blog</h1>

    <div v-for="(item, index) in articles" :key="index"
    class="card my-3">
      <div class="card-body">

        <nuxt-link :to="`blog/${item.id}`">
          <h1>{{item.title}}</h1>
        </nuxt-link>
        <p>{{item.body}}</p>

      </div>
    </div>


  </div>
</template>

<script>

import axios from 'axios';

export default {

  data(){
    return{
      articles: []
    }
  },

  async created(){

    try {

      const res = await axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10");

      this.articles = res.data;

    } catch (error) {
      console.log(error);
    }

  },

  components: {

  }
}
</script>
