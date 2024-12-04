<template>
  <div class="flex flex-col h-screen main-container">
    <NavBar />
    <main class="flex-1 overflow-auto">
      <RouterView />
    </main>
  </div>
</template>
<script setup lang="ts">
import NavBar from "@/components/NavBar.vue";
// import { gsap } from "gsap";
// import { onMounted } from "vue";
// onMounted(() => {
//   gsap.to(".main-container", {
//     padding: "12px",
//     duration: 0.5,
//   });
// });
</script>
