<template>
  <Suspense>
    <template #default>
      <MainLayout/>
    </template>

    <template #fallback>
      <div
          class="flex h-[100vh] w-full bg-[#0f172a]  items-center justify-center fixed top-0 z-[1000] ">
        <div class="flex items-center justify-center min-[576px]:gap-[15px] gap-[5px]">
          <img src="./assets/images/lion-coin.png" alt="" class="min-[576px]:h-[100px] h-[80px]">
          <span class="text-white min-[576px]:text-[95px] text-[65px]">LION</span>
        </div>
      </div>
    </template>
  </Suspense>
</template>

<script setup>
import MainLayout from "./layouts/MainLayout.vue";
import {ref} from "vue";

const checkLoad = ref(true)

setTimeout(() => {
  window.addEventListener('DOMContentLoaded', () => {
    checkLoad.value = false
  });
}, 3000)


</script>

<style>
.loadDone {
  display: none;
}



@keyframes hiddenLoad {
  0% {
    top: 0
  }
  100% {
    top: 100vh;
    display: none;
  }
}
</style>
