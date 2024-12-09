<script setup>
import {ref} from 'vue'
const message = ref("Hello Vuejs-3")

const space = ref(0);
function spacePressed(){
  space.value++;
  message.value = "Space pressed " + space.value + " times";
}

function whatKeyPressed(event){
  message.value = "You pressed " + event.key;
}

function buttonPressed(){
  message.value = "You pressed the left Button";
}

function secondButtonPressed(){
  message.value = "Your pressed Ctrl + right";
}

function divClicked(){
  alert("Div Clicked.");
}

function divButtonClicked(){
  alert("div button clicked");
}


</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Event and Modifiers handling in vuejs-3</h1>
    <h1 class="mt-10">{{ message}}</h1>
    <form @submit.prevent action="https://google.com/search">
      <div @keyup.space="spacePressed()" class="container mx-auto flex space-x-5 justify-cneter m-5">
        <input type="text" name="q" class="border border-gray-500 bg-white p-5" placeholder="Press Space">
      </div>
      <div @keyup="whatKeyPressed($event)" class="container mx-auto flex space-x-5 justify-cneter m-5">
        <input type="text" name="q" class="border border-gray-500 bg-white p-5" placeholder="Press any key">
      </div>
      <button @click.prevent="buttonPressed()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Button
      </button>
      <button @click.ctrl.right="secondButtonPressed()"  class="bg-blue-500 hover:bg-blue-700 ml-5 text-white font-bold py-2 px-4 rounded">
        Ctrl + Right
      </button>
     
    </form>

    <div @click="divClicked()"  class="bg-gray-200 w-[500px] h-80 mt-5 flex items-center justify-center">
      <button @click.stop="divButtonClicked()" class="bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded">Button</button>

    </div>


  </section>
</template>

<style scoped></style>
