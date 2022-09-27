<template>
  <div>
      <div class="card">
        <div class="w-50">
            <img  :src="isValidUrl(post.image_url) ? post.image_url : 'storage/' + post.image_url " class="card-img-top" alt="image-post"> 
        </div>
        <div>
            <h4>
                {{ post.title }}
            </h4>
            <h5>
                {{ post.user.name }}
            </h5>
        </div>
        <div class="card-body">
            <p class="card-text">
                {{ post.description }}
            </p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    props : ['post'],
    methods : {
        isValidUrl(str) {
            const regex = /(?:https?):\/\/(\w+:?\w*)?(\S+)(:\d+)?(\/|\/([\w#!:.?+=&%!\-\/]))?/;
            if(!regex .test(str)) {
                return false;
            } else {
                return true;
            }
        }
    }

}
</script>

<style>

</style>