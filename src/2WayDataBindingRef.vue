<script setup>
import { ref } from "vue";
const color = ref('None')

function setColor(){
  return {
    backgroundColor: color.value
  }
}


</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="my-10">
      <h1>Your expected color is : {{ color }}</h1>
      <input type="text" v-model="color">
    </div>
    <div class="w-16 h-16 mt-5" :style="setColor()"></div>
  </section>
</template>

<style scoped>

</style>
