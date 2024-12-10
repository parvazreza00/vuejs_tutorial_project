<script setup>
import { ref, reactive } from "vue";

const saarcCountries = reactive([
  { name: "Bangladesh", capital: "Dhaka" },
  { name: "Nepal", capital: "Kathmandu" },
  { name: "Bhutan", capital: "Thimphu" },
  { name: "Sri Lanka", capital: "Colombo" },
  { name: "India", capital: "New Delhi" },
  { name: "Pakistan", capital: "Islamabad" },
  { name: "Maldives", capital: "Male" },
]);

const capitals = [
  "Dhaka",
  "Kathmandu",
  "Thimphu",
  "Colombo",
  "New Delhi",
  "Islamabad",
  "Male",
];

function getRandomCapitals(){
  return capitals;
  // return capitals.sort(()=>Math.random()-0.5);
}

function getScore(){
  let score = 0;
  saarcCountries.forEach(country => {
    if(country.answer === country.capital){
      score++;
    }
  });

  return score;
}
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="mx-auto w-4/5">
      <p class="mb-10">{{ saarcCountries }}</p>
      <p class="mb-10">Your Score: {{ getScore() }}</p>

      <div
        class="my-5 border bordr-gray-400 p-5"
        v-for="(country, index) in saarcCountries"
        :key="country.name"
      >
        <p>{{ index + 1 }}. What is the capital of {{ country.name }}?</p>
        <template v-for="(capital,index) in getRandomCapitals()" :key="index">
          <input type="radio" :name="country.name" :value="capital" v-model="country.answer"/>
          <label for="" class="ml-2 mr-2">{{ capital }}</label>
        </template>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
