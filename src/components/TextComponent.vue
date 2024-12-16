<script setup>
const props = defineProps(["label", "modelValue"]);

const emit = defineEmits(["update:modelValue"]);
</script>

<template>
 <p>
<label>{{ label }}</label
  ><br />
  <input
    type="text"
    class="border border-gray-500"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
 </p>
</template>

<style scoped></style>
