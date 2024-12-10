<script setup>
import { ref, reactive } from "vue";

const favColors = ref([]);




</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="my-10">
      <h1>Colors: {{favColors}}</h1>
      <p>Your Favourite Colors</p>
      <label for="red">Red</label>   
      <input class="ml-2 mr-2" type="checkbox" id="red" v-model="favColors" value="red">    
      <label for="green">Green</label>   
      <input class="ml-2 mr-2" type="checkbox" id="green" v-model="favColors" value="green">    
      <label for="blue">Blue</label>   
      <input class="ml-2 mr-2" type="checkbox" id="blue" v-model="favColors" value="blue">    
    </div>
    
   
   
    
  </section>
</template>

<style scoped>

</style>
