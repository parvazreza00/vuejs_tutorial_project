<script setup>
import {reactive, ref} from 'vue';

const location = reactive(
  {
  name:"Dhaka",
  weather:"sunnny",
});

function geoLoacation(newlocation, weather){
  location.name = newlocation;
  location.weather = weather;
}



</script>

<template>
  <section class="container max-auto">
    <h1></h1>
    <div class="flex justify-center items-center space-x-3">
      <button @click="geoLoacation('Dhaka', 'Cloudy')" class="rounded-none bg-indigo-500 px-3 py-2 hover:bg-indigo-600">Dhaka</button>
      <button @click="geoLoacation('Rajshahi','Nice')" class="rounded-none bg-teal-500 px-3 py-2 hover:bg-teal-600">Rajshahi</button>
    </div>
   <h2>My Locatio is :{{ location.name }}, Weather: {{ location.weather }} </h2>
  </section>
</template>

<style scoped></style>
