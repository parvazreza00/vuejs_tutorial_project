<script setup>
import { ref, reactive } from "vue";

const displayImage = ref(true);




</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="my-10">
      <h1>{{displayImage}}</h1>   
      <input type="checkbox" v-model="displayImage">    
    </div>
    <div class="my-10">
      
      <img
      v-if="displayImage"
      class="mx-auto w-[500px] h-[400px] mt-10" 
      :src="`https://plus.unsplash.com/premium_photo-1666901328734-3c6eb9b6b979?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NXx8cmFuZG9tfGVufDB8fDB8fHww`" alt="">    
    </div>
   
    
  </section>
</template>

<style scoped>

</style>
