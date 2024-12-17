<script setup></script>

<template>
  <div class="ml-5 space-y-2 text-[20px] font-semibold">
      <div>
        <router-link :to="{name:'home'}">Home</router-link>
      </div>
      <div>
        <router-link :to="{name:'about'}">About</router-link>
      </div>
      <div>
        <router-link :to="{name:'blog'}">Blog</router-link>
      </div>
      <div>
        <router-link :to="{name:'contact'}">Contact</router-link>
      </div>
    </div>
</template>
