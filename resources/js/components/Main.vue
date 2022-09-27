<template>
  <div>
      aaaabbfytf
  </div>
</template>

<script>
// IMPORTIAMO AXIOS
import axios from 'axios'

export default {
name : 'app',

data : function(){
        return{
            postContent : [],
        }
    },

methods: {
        getPost : function(){
            console.log('POOYYOYOYOYO');
        },
    },
 created(){
       this.getPost();
    }
    
}
</script>

<style>

</style>