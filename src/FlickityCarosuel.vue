<script setup>
import { ref, onMounted, nextTick } from "vue";

const items = ref([
  "https://images.unsplash.com/photo-1725590137329-f182b5a8fac3?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw3fHx8ZW58MHx8fHx8",
  "https://images.unsplash.com/photo-1724592079766-dff978f52a17?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwxN3x8fGVufDB8fHx8fA%3D%3D",
  "https://images.unsplash.com/photo-1728327511538-e9624254ed84?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwyMnx8fGVufDB8fHx8fA%3D%3D",
  "https://images.unsplash.com/photo-1731613309340-eecea7c12ee3?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwzMHx8fGVufDB8fHx8fA%3D%3D",
  "https://plus.unsplash.com/premium_photo-1709311452215-496c6740ca59?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw0N3x8fGVufDB8fHx8fA%3D%3D",
]);

let carousel = null;

const newItem = ref(
  "https://images.unsplash.com/photo-1711991996886-d85765bf3d7d?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw1NXx8fGVufDB8fHx8fA%3D%3D"
);

function addNewitem() {
  items.value.push(newItem.value);
  carousel.destroy();
  nextTick(function(){
      carousel = new Flickity('#carousel',{});
  })
}

onMounted(() => {
  carousel = new Flickity("#carousel", {});
});
</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <div class="my-10">
      <input type="text" v-model="newItem">
      <button @click="addNewitem()" class="ml-2 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Button</button>
    </div>
    <div class="mx-auto items" id="carousel">
      <div
        :style="`background-image:url(${item})`"
        class="item text-center"
        v-for="(item, index) in items"
        :key="item"
      >
        {{ index + 1 }}
      </div>
    </div>
  </section>
</template>

<style scoped>
.items {
  width: 600px;
  height: 400px;
}

.item {
  width: 600px;
  height: 400px;
  background-color: #ccc;
  background-size: cover;
}
</style>
