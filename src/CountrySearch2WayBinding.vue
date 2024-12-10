<script setup>
import { ref, reactive } from "vue";
import {countries} from './data/countries'

const search = ref('');

function getFilteredCountries(){
  return countries.filter(country => {
    return country.name.toLowerCase().startsWith(search.value.toLowerCase());
  })
}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="mx-auto w-11/12 mt-10">
      <p class="text-2xl ml-12 py-6">{{ search }}</p>
      <p>
        search: <input type="text" class="border border-gray-400 px-2 py-2" v-model="search">
      </p>
      <p class="py-6">
        <ul>
          <li class="py-1.5" v-for="(country, index) in getFilteredCountries()" :key="country.name">
            {{ index +1 }}. {{ country.name }}
          </li>
        </ul>

      </p>
    </div>
  </section>
</template>

<style scoped></style>
