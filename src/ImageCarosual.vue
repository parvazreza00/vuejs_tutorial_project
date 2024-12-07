<script setup>
import {reactive, ref} from 'vue';

const fullImage = ref('https://images.pexels.com/photos/206359/pexels-photo-206359.jpeg?cs=srgb&dl=pexels-pixabay-206359.jpg&fm=jpg');

const images = [
  {
    thumb:'https://images.pexels.com/photos/206359/pexels-photo-206359.jpeg?cs=srgb&dl=pexels-pixabay-206359.jpg&fm=jpg',
    full:'https://images.pexels.com/photos/206359/pexels-photo-206359.jpeg?cs=srgb&dl=pexels-pixabay-206359.jpg&fm=jpg',
  },
  {
    thumb:'https://cdn.pixabay.com/photo/2022/07/12/07/06/lake-7316684_640.jpg',
    full:'https://cdn.pixabay.com/photo/2022/07/12/07/06/lake-7316684_640.jpg',
  },
  {
    thumb:'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29372.jpg',
    full:'https://img.freepik.com/free-photo/sunset-silhouettes-trees-mountains-generative-ai_169016-29372.jpg',
  },
  {
    thumb:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSRaIPqG4yFdOLLeqwstkU_7KRtsS95ZyXiWA&s',
    full:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSRaIPqG4yFdOLLeqwstkU_7KRtsS95ZyXiWA&s',
  }
]

function setImage(image){
  fullImage.value = image.full;
}

</script>

<template>
  <section class="container mx-auto flex itmes-center flex-col">
    <div class="w-11/12 mx-auto">
      <div class="flex space-x-2 grid grid-cols-4">
        <img @click="setImage(image)" class="w-64 h-28 cursor-pointer" v-for="image in images" :key="image.thum" :src="image.thumb">       
      </div>
      <div class="mt-10">
        <img class="mx-auto w-3/4 h-auto cursor-pointer" :src="fullImage" alt="">
      </div>
    </div>  
   

  </section>
</template>

<style scoped></style>
