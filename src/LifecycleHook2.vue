<script setup>
import { ref, onBeforeMount, onMounted, onUpdated } from "vue";

onUpdated(() => {
  console.log("App.vue updated");
});

const message = ref("hello world");
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="flex justify-between mt-20">
      <h1 class="text-center text-2xl py-10">{{ message }}</h1>
      
    </div>
    <button @click="message='Hello form Ostad!'">Update Message</button>
  </section>
</template>

<style scoped></style>
