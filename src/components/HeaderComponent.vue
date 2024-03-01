<template>
  <div class="bg-[#0F172A] flex relative">
    <div
        class="container py-[13.45px] min-[768px]:py-[24px] w-full mx-auto flex justify-between items-center relative z-30">
      <div class="flex-shrink-0 flex items-center">
        <img src="../assets/images/Logo.png" alt="" class="h-[33px] min-[992px]:h-[40px] min-[1200px]:h-[48px]">
      </div>
      <div class="hidden min-[768px]:block border-r h-full border-[#1E293B]"></div>
      <div
          class="hidden min-[768px]:flex items-center max-w-[430px] min-[992px]:max-w-[535px] min-[1200px]:max-w-[634px] w-full justify-between text-white text-[14px] min-[992px]:text-[16px] min-[1200px]:text-[18px] leading-[26px] font-[300]"
      >
        <span class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]">Home</span>
        <span class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]">What is Lion?</span>
        <span class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]">Buying Guide</span>
        <span class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]">Tokenomics</span>
        <span class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]">Roadmap</span>
        <span class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]">Whitepaper</span>
      </div>
      <div class="hidden min-[768px]:block border-r h-full border-[#1E293B]"></div>
      <button
          class="hidden min-[768px]:flex items-center justify-center py-[5px] px-[9px] rounded-full gap-[4px] bg-[#FF4800]
           h-[33px] w-[115px] min-[992px]:h-[40px] min-[992px]:w-[130px] min-[1200px]:h-[48px] min-[1200px]:w-[165px]"
      >
        <span
            class="text-white text-[12px] min-[1200px]:text-[18px] min-[992px]:text-[14px] leading-[26px] font-[300]">Get Lion Now</span>
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
          <path
              d="M13.4767 9.1664L9.00668 4.6964L10.185 3.51807L16.6667 9.99973L10.185 16.4814L9.00668 15.3031L13.4767 10.8331H3.33334V9.1664H13.4767Z"
              fill="white"/>
        </svg>
      </button>
      <button class="block min-[768px]:hidden h-fit w-fit" @click="handleShowMenu">
        <img v-if="!showMenu" src="../assets/images/menu-btn.png" alt="" width="32">
        <img v-else src="../assets/images/btn-close.png" alt="">
      </button>

    </div>
    <div
        :class="{'show':showMenu}"
        class="flex flex-col absolute right-0 left-0 bottom-0 top-[60px] bg-[#0F172A] h-[100vh]
        z-20 menu-mobile min-[768px]:hidden"
    >
      <div class="container flex flex-col gap-[24px]">
        <div class="flex flex-col">
          <div class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white"
               @click="handleShowMenu">Home
          </div>
          <div class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white"
               @click="handleShowMenu">What is
            Lion?
          </div>
          <div class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white"
               @click="handleShowMenu">Buying
            Guide
          </div>
          <div class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white"
               @click="handleShowMenu">
            Tokenomics
          </div>
          <div class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white"
               @click="handleShowMenu">Roadmap
          </div>
          <div class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white"
               @click="handleShowMenu">
            Whitepaper
          </div>
        </div>
        <button
            @click="handleShowMenu"
            class="w-full bg-[#FF4800] text-white text-[18px] flex justify-center gap-[8px] items-center py-[10px] px-[24px] rounded-full">
          Get Lion Now
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path
                d="M13.4767 9.1664L9.00671 4.6964L10.185 3.51807L16.6667 9.99973L10.185 16.4814L9.00671 15.3031L13.4767 10.8331H3.33337V9.1664H13.4767Z"
                fill="white"/>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import {ref, watch} from "vue";

const showMenu = ref(false)

const handleShowMenu = () => {
  showMenu.value = !showMenu.value
}

// watch(showMenu, (newValue) => {
//   const menuElement = document.querySelector('.menu-mobile');
//   if (menuElement) {
//     if (newValue) {
//       menuElement.classList.add('show');
//     } else {
//       menuElement.classList.remove('show');
//     }
//   }
// });

</script>

<style>
.menu-mobile {
  transition: top 0.3s ease-in-out;

}

.menu-mobile {
  top: -100vh;
  opacity: 0;
}


.menu-mobile.show {
  top: 60px;
  opacity: 1;
}
</style>
