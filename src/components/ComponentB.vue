<script setup>
import { provide } from 'vue'
import {course} from '../data/course.js'
import ComponentC from './ComponentC.vue'

provide('course-stock', 500);

</script>

<template>
  <p>Course Name in component B: {{ course.name }}</p>
  <p class="ml-10">
    <ComponentC />
  </p>
</template>
