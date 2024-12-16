<script setup>
const props = defineProps([
    'fname' , 'lname'
])

const emit = defineEmits(['update:fname' , 'update:lname'])



</script>

<template>
    <div>
        <label for="">First Name</label><br>
        <input type="text" class="border border-gray-500 hover:border-blue-400" :value="fname" @input="$emit('update:fname', $event.target.value)"><br>
        <label for="">Last Name</label><br>
        <input type="text" class="border border-gray-500 hover:border-blue-400" :value="lname" @input="$emit('update:lname', $event.target.value)">
    </div>
</template>