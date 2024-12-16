<script setup>
import { inject } from 'vue'
import { course } from '../data/course.js'
const stock = inject('course-stock');
</script>

<template>
  <p>Course Name in component C: {{ course.name }}</p>
  <p class="ml-10">
    <input type="text" class="border border-gray-500" v-model="course.name">
  </p>
  <p>
   course-stock : {{ stock }}
  </p>
</template>
