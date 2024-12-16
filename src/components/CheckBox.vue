<script setup>
const props = defineProps(['modelValue', 'label']);

const emit = defineEmits(['update:modelValue']);
</script>

<template>
    <div>
        <label for="">{{label}}</label>
        <input type="checkbox" class="ml-5" :checked="modelValue" @change="$emit('update:modelValue', !modelValue)" >
    </div>
</template>
