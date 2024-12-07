<script setup>
import {reactive, ref} from 'vue';

const activeIndex = ref(0);

const accordions = reactive([
  {
    heading:'Some Heading',
    content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam accusamus libero, nam quae id possimus, beatae praesentium ducimus recusandae expedita veritatis aliquid minus a tempora. Laudantium, voluptatum. Ad quam reiciendis quis sint aliquid ullam, possimus doloribus nihil tempore. Rerum culpa mollitia dolorem. Dolorum enim reprehenderit quibusdam obcaecati ratione nulla veritatis.',
    isOpen:false
  },
  {
    heading:'How to use Accordian??',
    content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam accusamus libero, nam quae id possimus, beatae praesentium ducimus recusandae expedita veritatis aliquid minus a tempora. Laudantium, voluptatum. Ad quam reiciendis quis sint aliquid ullam, possimus doloribus nihil tempore. Rerum culpa mollitia dolorem. Dolorum enim reprehenderit quibusdam obcaecati ratione nulla veritatis.',
    isOpen:false
  },
  {
    heading:'Where i use Accordian?',
    content:'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam accusamus libero, nam quae id possimus, beatae praesentium ducimus recusandae expedita veritatis aliquid minus a tempora. Laudantium, voluptatum. Ad quam reiciendis quis sint aliquid ullam, possimus doloribus nihil tempore. Rerum culpa mollitia dolorem. Dolorum enim reprehenderit quibusdam obcaecati ratione nulla veritatis.',
    isOpen:false
  }
])





</script>

<template>
  <section class="container max-auto">

    <div class="transition hover:bg-indigo-200" v-for="accordion in accordions" :key="accordion.index">
      <!-- header -->
      <div @click="accordion.isOpen=!accordion.isOpen" class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16">
        <i class="fa-solid fa-plus"></i>
        <h3>{{ accordion.heading }}</h3>
      </div>
      <!-- content -->
      <div class="px-5 pt-0 text-left pb-5" v-show="accordion.isOpen">
        <p class="leading-6 font-light pl-9">
         {{ accordion.content }}
        </p>
      </div>
    </div>
    <p>---------------------------------------------------------------</p>


    <div class="transition hover:bg-indigo-200" v-for="(accordion, index) in accordions" :key="index">
      <!-- header -->
      <div @click="activeIndex=index" class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16">
        <i class="fa-solid fa-plus"></i>
        <h3>{{ accordion.heading }}</h3>
      </div>
      <!-- content -->
      <div class="px-5 pt-0 text-left pb-5" v-show="index==activeIndex">
        <p class="leading-6 font-light pl-9">
         {{ accordion.content }}
        </p>
      </div>
    </div>

   

  </section>
</template>

<style scoped></style>
