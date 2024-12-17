<script setup>
import { reactive, ref, provide } from "vue";
import Sidebar from "./components/Sidebar.vue";
</script>

<template>
  <!-- header start -->
  <section class="container mx-auto">
    <header class="">
      <div class="bg-black">
        <h1 class="text-white px-5 py-3">WonderFul Blog Site</h1>
      </div>
    </header>
  </section>
  <!-- header end -->

  <section class="container mx-auto flex">
    <!-- sidbar start -->
    <div>
      <aside class="md:w-[300px] sm:w-[150px] bg-gray-100 h-screen pt-5">
        <Sidebar></Sidebar>
      </aside>
    </div>
    <!-- sidbar end -->

    <!-- main content start -->
    <div class="w-full bg-gray-50 h-dvh pt-5">
      <router-view></router-view>
    </div>
    <!-- main content end -->

    <!-- <RightSidebar></RightSidebar> -->
    <router-view name="right"></router-view>

    
  </section>
</template>
