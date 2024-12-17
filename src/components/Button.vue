<script setup>
const props = defineProps(['label']); 

</script>


<template>
    <button class="bg-blue-500 hover:bg-blue-600 p-4 ml-2">
        <div class="flex items-center">
            <slot name="licon"></slot>
            <span class="mx-2">
                <slot>Click Me</slot>
            </span>
            <slot name="ricon"></slot>
        </div>
    </button>
</template>