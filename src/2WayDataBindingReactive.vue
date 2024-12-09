<script setup>
import { ref, reactive } from "vue";

const person = reactive(
  {
    name:"parvaz reza",
    age:28,
    job:"SE",
  }
)



</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="my-10">
      <h1>{{person}}</h1>      
    </div>
    <div class="mb-2" v-for="(value, key, index) in person" :key="index">
      <p class="">{{ key }}</p>
      <input type="text" class="border border-gray-300 rounded-md p-2" v-model="person[key]">
    </div>
    
  </section>
</template>

<style scoped>

</style>
