<script setup>
import { ref } from 'vue';
const props = defineProps(['modelValue']);
const nameSplit = props.modelValue.split(" ");
const fname = ref(nameSplit[0]);
const lname = ref(nameSplit[1]);

const emit = defineEmits(['update:modelValue']);
const updateName = ()=>{
    emit('update:modelValue', `${fname.value} ${lname.value}`);
}

</script>

<template>
    <div>
        <label for="">First Name</label><br>
        <input type="text" class="border border-gray-500 " v-model="fname" @input="updateName()"><br>
        <label for="">Last Name</label><br>
        <input type="text" class="border border-gray-500 " v-model="lname" @input="updateName()">
    </div>
</template>