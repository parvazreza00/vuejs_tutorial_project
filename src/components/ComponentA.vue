<script setup>
import {course} from '../data/course.js'
import ComponentB from './ComponentB.vue'

// const course = inject('course')
// provide('course-stock', 500);

</script>


<template>
<p class="ml-5">
    Course Name in component A: {{ course.name }}
</p>
<p class="ml-10">
    <ComponentB  />
</p>

    
</template>