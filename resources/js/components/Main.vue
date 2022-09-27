<template>
  <div class="container">
      <div class="row">
              <postCard v-for="post in posts" :key="post.id" :post="post"/>
      </div>
  </div>
</template>

<script>
// IMPORTIAMO AXIOS
import axios from 'axios'
import postCard from './MainComponents/PostCard.vue'

export default {
name : 'app',
components: {
        postCard
    },
data : function(){
        return{
            posts : [],
        }
    },

methods: {
        getPost : function(){
            axios.get('api/post')
            .then((elemet)=> {
                this.posts = elemet.data.resoult ;
            })
            .catch((error) => {
                console.log(error);
            })
        },
    },
 created(){
       this.getPost();
    }

}
</script>

<style>

</style>