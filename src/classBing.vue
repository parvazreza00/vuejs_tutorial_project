<script setup>
import { ref } from "vue";

const bgOrange = "bg-orange-400";
const bgIndigo = "bg-gray-400";
const bgGreen = "bg-red-400";

const colors = {
  bgColor: 'bg-teal-100',
  borderColor:'border-teal-500',
  textColor:'text-teal-900',
}

const messageType = 'warning';

if('error'==messageType){
  colors.bgColor = 'bg-red-100';
  colors.borderColor = 'border-red-500';
  colors.textColor = 'text-red-900';
}

if('warning'==messageType){
   colors.bgColor = 'bg-orange-100';
  colors.borderColor = 'border-orange-500';
  colors.textColor = 'text-orange-900';
}

const weekday = true;

</script>

<template>
  <section class="container max-auto">
    <section class="flex justify-center max-auto space-x-10 mt-10">
      <div class="w-1/4 h-16" :class="bgOrange"></div>
      <div class="w-1/4 bg-indigo-400 h-16" :class="bgIndigo"></div>
      <div class="w-1/4 h-16" :class="bgGreen"></div>
    </section>
    <section class="mt-10">
      <div class="h-16 flex items-center justify-center text-white" :class="[weekday ? 'bg-red-400' : 'bg-green-400', weekday ? 'text-7xl' : 'text-2xl']">
        <h1>It's a weekday</h1>
      </div>
    </section>

    <section class="mt-10 flex justify-center">
      <div class="w-1/2 border-t-4 rounded-b px-4 py-3 shadow-md" :class="[colors.bgColor, colors.borderColor, colors.textColor]"> 
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
}
</style>
