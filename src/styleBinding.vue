<script setup>
import { ref } from "vue";

const bgOrange = "background-color:rgb(241, 173, 45)";
const bgIndigo = "background-color:rgb(136, 44, 202)";
const bgRed = "background-color:rgb(202, 44, 44)";
const bgGreen = "background-color:rgb(44, 202, 65)";

const colors = {
  backgroundColor: 'green',
  color: 'red',
  borderColor: 'yellow',
};

const messageType = 'warning';

if('error'==messageType){
  colors.backgroundColor = 'blue';
  colors.color = 'orange';
  colors.borderColor = 'red';
}

if('warning'==messageType){
   colors.backgroundColor = 'orange';
  colors.borderColor = 'blue';
  colors.color = 'red';
}

const weekday = true;

</script>

<template>
  <section class="container max-auto">
    <section class="flex justify-center max-auto space-x-10 mt-10">
      <div class="w-1/4 h-16" :style="bgOrange"></div>
      <div class="w-1/4 h-16" :style="bgIndigo"></div>
      <div class="w-1/4 h-16" :style="bgRed"></div>
    </section>
    <section class="mt-10">
      <!-- <div class="h-16 flex items-center justify-center text-white" 
      :style="weekday ? [bgRed,'font-size:25px'] : [bgGreen, 'font-size:35px']"> -->
      <div class="h-16 flex items-center justify-center text-white" 
      :style="[weekday ? bgRed : bgGreen, weekday ? 'font-size:16px' : 'font-size:40px']">
        <h1>It's a weekday</h1>        
      </div>
    </section>

    <section class="mt-10 flex justify-center">
      <div class="w-1/2 border-t-4 rounded-b px-4 py-3 shadow-md" :style="colors"> 
        <p class="font-bold">Our privaciy policy has changed</p>
        <p class="text-sm">Make sure you know hese changes affect you.</p>
      </div>

    </section>

  </section>
</template>

<style scoped>
img {
  border: 2px solid rgb(226, 206, 206);
  padding: 5px;
  border-radius: 8px;
  max-width: 100%;
  height: 300px;
  margin: auto;
  color:rgba(9, 58, 58,4)
}
</style>
