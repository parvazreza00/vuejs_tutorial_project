<script setup>
import TextComponent from "./TextComponent.vue"
const props = defineProps(['person'])
</script>

<template>
    <p>
        <TextComponent label="Name" v-model="person.name" />
        <TextComponent label="Email" v-model="person.email" />
        
    </p>
</template>