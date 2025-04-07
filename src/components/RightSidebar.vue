<script setup>
const rightsidebar = "bg-teal-100 p-2 space-y-2";
</script>

<template>
  <div>
    <aside class="md:w-[300px] sm:w-[150px] bg-gray-100 h-screen pt-5">
      <div class="ml-5 space-y-2 text-[20px] font-semibold">
        <div :class="rightsidebar">Travel</div>
        <div :class="rightsidebar">Jumpping</div>
        <div :class="rightsidebar">Swimming</div>
        <div :class="rightsidebar">Hicking</div>
      </div>
    </aside>
  </div>
</template>
