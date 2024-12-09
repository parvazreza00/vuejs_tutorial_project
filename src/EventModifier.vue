<script setup>
import {ref} from 'vue'

const about = ref('home');
const links = [
  {
    name:"Google",
    url: 'https://www.google.com/',
    about:'Google LLC (/ˈɡuːɡəl/ GOO-gəl) is an American-based multinational corporation and technology company focusing on online advertising, search engine technology, cloud computing, computer software, quantum computing, e-commerce, consumer electronics, and artificial intelligence (AI).',
  },
  {
    name:"Facebook",
    url: 'https://www.facebook.com/',
    about:'Facebook is a social media and social networking service owned by American technology conglomerate Meta. Created in 2004 by Mark Zuckerberg.',
  },
  {
    name:"twitter",
    url: 'https://www.twitter.com/',
    about:'Twitter is a social networking site that allows users to share short messages, known as tweets, with other users.',
  },
];

function setText(text){
  about.value = text;
}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Evens and Reactivity in vuejs</h1>
    <h1 class="mt-10">{{ about }}</h1>
    <div class="container mx-auto flex space-x-5 justify-center m-[1000px]">
      <a
      v-for="(link) in links" 
      :key="link.name"
      @click.prevent="setText(link.about)" 
      href="#">{{ link.name }}</a>
    </div>
  </section>
</template>

<style scoped></style>
