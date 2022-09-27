<template>
  <div class="my-4 col-6 ">
      <div class="card m-3">
        <div class="card-img d-flex justify-content-center">
            <img  :src="isValidUrl(post.image_url) ? post.image_url : 'storage/' + post.image_url " class="card-img-top" alt="image-post"> 
        </div>
        <div class="card-body">
            <h4>
                {{ post.title }}
            </h4>
            <h5>
                {{ post.user.name }}
            </h5>
            <div class="category-text">
                {{ post.category.name }}
            </div>
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
.card{
    height: 100%;
}
.card-img{
    height: 300px;
}
img{
    object-fit: cover;
}

</style>