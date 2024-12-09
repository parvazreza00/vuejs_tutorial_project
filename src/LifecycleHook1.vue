<script setup>
import { ref, onBeforeMount, onMounted } from "vue";

const status = ref([]);
const apiResponse = ref(null);

onBeforeMount(()=>{
  console.log("before mount");
  status.value.push('before mount');

  fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(json => {
    apiResponse.value = json
  })
});

onMounted(()=>{
  console.log('mounted');
  status.value.push('mounted');
});
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">LifeCycle Hooks</h1>

    <div class="flex justify-between mt-20">
      <div class="w-1/2">
        <img src="https://vuejs.org/assets/lifecycle.MuZLBFAS.png" alt="" />
      </div>
      <div class="text-2xl w-1/2">
      {{ status }}

      </div>

      <div>
        {{ apiResponse }}
      </div>
    </div>
  </section>
</template>

<style scoped></style>
