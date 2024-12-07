<script setup>
import {reactive, ref} from 'vue';

const accordionIndex = ref(0);

const accordions = reactive(
  [
  false, false, false, false
]
);

function toggle(index){
  accordions[index] = !accordions[index];
}



</script>

<template>
  <section class="container max-auto">

    <div class="transition hover:bg-indigo-200">
      <!-- header -->
      <div @click="toggle(0)" class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16">
        <i class="fa-solid fa-plus"></i>
        <h3>Some Heading</h3>
      </div>
      <!-- content -->
      <div class="px-5 pt-0 text-left pb-5" v-show="accordions[0]">
        <p class="leading-6 font-light pl-9">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam accusamus libero, nam quae id possimus, beatae praesentium ducimus recusandae expedita veritatis aliquid minus a tempora. Laudantium, voluptatum. Ad quam reiciendis quis sint aliquid ullam, possimus doloribus nihil tempore. Rerum culpa mollitia dolorem. Dolorum enim reprehenderit quibusdam obcaecati ratione nulla veritatis.
        </p>
      </div>
    </div>

    <div class="transition hover:bg-indigo-200">
      <!-- header -->
      <div @click="toggle(1)" class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16">
        <i class="fa-solid fa-plus"></i>
        <h3>Terms and conditions?</h3>
      </div>
      <!-- content -->
      <div class="px-5 pt-0 text-left pb-5" v-show="accordions[1]">
        <p class="leading-6 font-light pl-9">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam accusamus libero, nam quae id possimus, beatae praesentium ducimus recusandae expedita veritatis aliquid minus a tempora. Laudantium, voluptatum. Ad quam reiciendis quis sint aliquid ullam, possimus doloribus nihil tempore. Rerum culpa mollitia dolorem. Dolorum enim reprehenderit quibusdam obcaecati ratione nulla veritatis.
        </p>
      </div>
    </div>

    <div class="transition hover:bg-indigo-200">
      <!-- header -->
      <div  @click="accordions[2]=!accordions[2]"  class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16">
        <i class="fa-solid fa-plus"></i>
        <h3>How i use accordions?</h3>
      </div>
      <!-- content -->
      <div class="px-5 pt-0 text-left pb-5" v-show="accordions[2]">
        <p class="leading-6 font-light pl-9">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam accusamus libero, nam quae id possimus, beatae praesentium ducimus recusandae expedita veritatis aliquid minus a tempora. Laudantium, voluptatum. Ad quam reiciendis quis sint aliquid ullam, possimus doloribus nihil tempore. Rerum culpa mollitia dolorem. Dolorum enim reprehenderit quibusdam obcaecati ratione nulla veritatis.
        </p>
      </div>
    </div>

  </section>
</template>

<style scoped></style>
