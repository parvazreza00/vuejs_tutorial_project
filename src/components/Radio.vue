<script setup>
import { computed } from "vue";

const props = defineProps([
    'label','modelValue','value'
])


const emit = defineEmits(['update:modelValue']);

const radioValue = computed({
    get:() => props.modelValue,
    set: (value) => emit('update:modelValue', value)
})


</script>


<template>
    <div>
        <label for="">{{ label }}</label>
        <input type="radio" class="ml-2" :value="value" v-model="radioValue">
    </div>
</template>