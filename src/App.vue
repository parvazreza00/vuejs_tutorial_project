<script setup>
import { reactive, ref, provide } from "vue";
import {course} from './data/course.js'
import PersonComponent from "./components/PersonComponent.vue";
import NameComponent from "./components/NameComponent.vue";
import TextComponent from "./components/TextComponent.vue";
import NameComponentX from "./components/NameComponentX.vue";
import CheckBox from "./components/CheckBox.vue";
import Radio from "./components/Radio.vue";
import ComponentA from "./components/ComponentA.vue";

const person = reactive({
  name: "jone doe",
  email: "jone@doe.com",
});

const fname = ref("Jone");
const lname = ref("Doe");

const fulName = ref("Jone Doe");
const fulEmail = ref("jone@doe.com");

const taskDone = ref(false);

const fruit = ref("apple");




</script>

<template> 
  <div>
    
     <label for="" class="text-2xl">From Component</label>
     <h1 class="font-bold underline underline-offset-2">Props drilling</h1>
     <p>
      <ComponentA />
     </p>
     <p>
      
     </p>
  </div>
</template>
