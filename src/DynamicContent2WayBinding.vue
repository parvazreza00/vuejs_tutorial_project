<script setup>
import { ref, reactive } from "vue";

const persons = reactive([
  {name:"John Doe", age:26, email:"john@doe.com"},
  {name:"Jasin Doe", age:24, email:"jashin@doe.com"},
  {name:"Hasin Doe", age:26, email:"hasin@dgmail.com"},
  {name:"Takin Doe", age:26, email:"takin@gmail.com"},
]);

const activeIndex = ref(0);
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="mx-auto w-11/12">
      <p class="my-5">{{ persons }}</p>

      <div class="flex">
        <div class="w-1/2">
        <p>{{ activeIndex }}</p>
        <p class="mb-10">
          <h2>Select a person</h2>
          <select class="border border-gray-400 px-2" name="person" id="person" v-model="activeIndex">
            <option :value="index" v-for="(person, index) in persons" :key="index">{{person.name}}</option>
          </select>

        </p>
        </div>
        <div class="flex flex-col">
          <input type="text" class="my-3 border border-gray-400 py-2 px-4" :placeholder="key"  v-model="persons[activeIndex][key]" v-for="(value, key, index2) in persons[activeIndex]" :key="key">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
