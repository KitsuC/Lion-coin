<template>
  <div class="top-0 right-0 left-0 w-full z-50">
    <div class="bg-[#0F172A] flex relative">
      <div
        class="container py-[13.45px] min-[768px]:py-[24px] w-full mx-auto flex justify-between items-center relative z-30">
        <div class="flex-shrink-0 flex items-center">
          <img src="../assets/images/Logo.svg" alt="" class="h-[33px] min-[992px]:h-[40px] min-[1200px]:h-[48px]">
        </div>
        <div class="hidden min-[768px]:block border-r h-full border-[#1E293B]"></div>
        <div
          class="hidden min-[768px]:flex items-center max-w-[430px] min-[992px]:max-w-[535px] min-[1200px]:max-w-[634px] w-full justify-between text-white text-[14px] min-[992px]:text-[16px] min-[1200px]:text-[18px] leading-[26px] font-[300]">
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('home')">
            Home
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('whatislion')">
            What is Lion?
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('buyingguide')">
            Buying Guide
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-3000 hover:text-[#FF4800]"
            @click="scrollToSection('tokenomics')">
            Tokenomics
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('roadmap')">
            Roadmap
          </button>
          <!--        <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"-->
          <!--                @click="scrollToSection('whitepaper')">-->
          <!--          Whitepaper-->
          <!--        </button>-->
        </div>
        <div class="hidden min-[768px]:block border-r h-full border-[#1E293B]"></div>
        <button
          class="hidden min-[768px]:flex items-center justify-center py-[5px] px-[9px] rounded-full gap-[4px] bg-[#FF4800]
               h-[33px] w-[115px] min-[992px]:h-[40px] min-[992px]:w-[130px] min-[1200px]:h-[48px] min-[1200px]:w-[165px] ease-linear duration-300 hover:opacity-[0.8]"
          @click="handlePopup">
          <span
            class="text-white text-[12px] min-[1200px]:text-[18px] min-[992px]:text-[14px] leading-[26px] font-[300] ">
            Get Lion Now
          </span>
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path
              d="M13.4767 9.1664L9.00668 4.6964L10.185 3.51807L16.6667 9.99973L10.185 16.4814L9.00668 15.3031L13.4767 10.8331H3.33334V9.1664H13.4767Z"
              fill="white" />
          </svg>
        </button>
        <button
          class="block min-[768px]:hidden h-[32px] w-[32px] flex justify-center items-center rounded-full bg-[#FF4800]"
          @click="handleShowMenu">
          <svg v-if="!showMenu" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20"
            fill="none">
            <path
              d="M2.5 3.33325H17.5V4.99992H2.5V3.33325ZM2.5 9.16658H17.5V10.8333H2.5V9.16658ZM2.5 14.9999H17.5V16.6666H2.5V14.9999Z"
              fill="white" />
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path
              d="M9.99999 8.82153L14.125 4.69653L15.3033 5.87487L11.1783 9.99987L15.3033 14.1249L14.125 15.3032L9.99999 11.1782L5.87499 15.3032L4.69666 14.1249L8.82166 9.99987L4.69666 5.87487L5.87499 4.69653L9.99999 8.82153Z"
              fill="white" />
          </svg>
        </button>

      </div>
      <div :class="{ 'show': showMenu }" class="flex flex-col absolute right-0 left-0 bottom-0 top-[60px] bg-[#0F172A] h-[100vh]
            z-20 menu-mobile min-[768px]:hidden">
        <div class="container flex flex-col gap-[24px]">
          <div class="flex flex-col gap-[12px]">
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('home')">Home
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('whatislion')">
              What is Lion?
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('buyingguide')">
              Buying Guide
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('tokenomics')">
              Tokenomics
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('roadmap')">Roadmap
            </div>
            <!--          <div-->
            <!--              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"-->
            <!--              @click="scrollToSection('whitepaper')">-->
            <!--            Whitepaper-->
            <!--          </div>-->
          </div>
          <button @click="handlePopup"
            class="w-full bg-[#FF4800] text-white text-[18px] flex justify-center gap-[8px] items-center py-[10px] px-[24px] rounded-full font-[300] duration-300 ease-linear hover:opacity-[0.8]">
            Get Lion Now
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path
                d="M13.4767 9.1664L9.00671 4.6964L10.185 3.51807L16.6667 9.99973L10.185 16.4814L9.00671 15.3031L13.4767 10.8331H3.33337V9.1664H13.4767Z"
                fill="white" />
            </svg>
          </button>
        </div>
      </div>
      <div :class="{ 'showPopup': showPopup }"
        class="hidden fixed top-0 right-0 left-0 bottom-0 w-full h-[100vh] z-50 bg-blur justify-center items-center bg-opacity">
        <div :class="{ 'popupShow': showPopup }"
          class="flex justify-center items-center bg-[#0F172A] p-[30px] rounded-[12px] flex-col w-[400px] gap-[10px] popup ">
          <button
            class="self-end h-[32px] w-[32px] flex justify-center items-center rounded-full bg-[#FF4800]"
            @click="handleShowMenu">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path
                d="M9.99999 8.82153L14.125 4.69653L15.3033 5.87487L11.1783 9.99987L15.3033 14.1249L14.125 15.3032L9.99999 11.1782L5.87499 15.3032L4.69666 14.1249L8.82166 9.99987L4.69666 5.87487L5.87499 4.69653L9.99999 8.82153Z"
                fill="white" />
            </svg>
          </button>
          <h2 class="text-[42px] leading-[48px] text-white mb-[20px]">Coming soon</h2>
          <button class="bg-[#FF4800] rounded-full text-white p-[10px] w-full text-[24px] leading-[32px]"
            @click="handlePopup">Close
          </button>
        </div>
      </div>
    </div>
  </div>
  <div :class="{ '!h-auto': showHeader, '!opacity-100': showHeader }"
    class="top-0 right-0 left-0 w-full z-50 sticky-header">
    <div class="bg-[#0F172A] flex relative">
      <div
        class="container py-[13.45px] min-[768px]:py-[24px] w-full mx-auto flex justify-between items-center relative z-30">
        <div class="flex-shrink-0 flex items-center">
          <img src="../assets/images/Logo.svg" alt="" class="h-[33px] min-[992px]:h-[40px] min-[1200px]:h-[48px]">
        </div>
        <div class="hidden min-[768px]:block border-r h-full border-[#1E293B]"></div>
        <div
          class="hidden min-[768px]:flex items-center max-w-[430px] min-[992px]:max-w-[535px] min-[1200px]:max-w-[634px] w-full justify-between text-white text-[14px] min-[992px]:text-[16px] min-[1200px]:text-[18px] leading-[26px] font-[300]">
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('home')">
            Home
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('whatislion')">
            What is Lion?
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('buyingguide')">
            Buying Guide
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-3000 hover:text-[#FF4800]"
            @click="scrollToSection('tokenomics')">
            Tokenomics
          </button>
          <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"
            @click="scrollToSection('roadmap')">
            Roadmap
          </button>
          <!--        <button class="py-[4px] px-[6px] cursor-pointer duration-300 hover:text-[#FF4800]"-->
          <!--                @click="scrollToSection('whitepaper')">-->
          <!--          Whitepaper-->
          <!--        </button>-->
        </div>
        <div class="hidden min-[768px]:block border-r h-full border-[#1E293B]"></div>
        <button
          class="hidden min-[768px]:flex items-center justify-center py-[5px] px-[9px] rounded-full gap-[4px] bg-[#FF4800]
               h-[33px] w-[115px] min-[992px]:h-[40px] min-[992px]:w-[130px] min-[1200px]:h-[48px] min-[1200px]:w-[165px] ease-linear duration-300 hover:opacity-[0.8]"
          @click="handlePopup">
          <span
            class="text-white text-[12px] min-[1200px]:text-[18px] min-[992px]:text-[14px] leading-[26px] font-[300] ">
            Get Lion Now
          </span>
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path
              d="M13.4767 9.1664L9.00668 4.6964L10.185 3.51807L16.6667 9.99973L10.185 16.4814L9.00668 15.3031L13.4767 10.8331H3.33334V9.1664H13.4767Z"
              fill="white" />
          </svg>
        </button>
        <button
          class="block min-[768px]:hidden h-[32px] w-[32px] flex justify-center items-center rounded-full bg-[#FF4800]"
          @click="handleShowMenu">
          <svg v-if="!showMenu" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20"
            fill="none">
            <path
              d="M2.5 3.33325H17.5V4.99992H2.5V3.33325ZM2.5 9.16658H17.5V10.8333H2.5V9.16658ZM2.5 14.9999H17.5V16.6666H2.5V14.9999Z"
              fill="white" />
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path
              d="M9.99999 8.82153L14.125 4.69653L15.3033 5.87487L11.1783 9.99987L15.3033 14.1249L14.125 15.3032L9.99999 11.1782L5.87499 15.3032L4.69666 14.1249L8.82166 9.99987L4.69666 5.87487L5.87499 4.69653L9.99999 8.82153Z"
              fill="white" />
          </svg>
        </button>

      </div>
      <div :class="{ 'show': showMenu }" class="flex flex-col absolute right-0 left-0 bottom-0 top-[60px] bg-[#0F172A] h-[100vh]
            z-20 menu-mobile min-[768px]:hidden">
        <div class="container flex flex-col gap-[24px]">
          <div class="flex flex-col gap-[12px]">
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('home')">Home
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('whatislion')">
              What is Lion?
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('buyingguide')">
              Buying Guide
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('tokenomics')">
              Tokenomics
            </div>
            <div
              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"
              @click="scrollToSection('roadmap')">Roadmap
            </div>
            <!--          <div-->
            <!--              class="py-[8px] px-[12px] text-[18px] leading-[26px] font-[300] w-full text-center text-white hover:text-[#FF4800]"-->
            <!--              @click="scrollToSection('whitepaper')">-->
            <!--            Whitepaper-->
            <!--          </div>-->
          </div>
          <button @click="handlePopup"
            class="w-full bg-[#FF4800] text-white text-[18px] flex justify-center gap-[8px] items-center py-[10px] px-[24px] rounded-full font-[300] duration-300 ease-linear hover:opacity-[0.8]">
            Get Lion Now
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path
                d="M13.4767 9.1664L9.00671 4.6964L10.185 3.51807L16.6667 9.99973L10.185 16.4814L9.00671 15.3031L13.4767 10.8331H3.33337V9.1664H13.4767Z"
                fill="white" />
            </svg>
          </button>
        </div>
      </div>
      <div :class="{ 'showPopup': showPopup }"
        class="hidden fixed top-0 right-0 left-0 bottom-0 w-full h-[100vh] z-50 bg-blur justify-center items-center bg-opacity">
        <div :class="{ 'popupShow': showPopup }"
          class="flex justify-center items-center bg-[#0F172A] p-[30px] rounded-[12px] flex-col w-[400px] gap-[10px] popup ">
          <button
            class="self-end h-[32px] w-[32px] flex justify-center items-center rounded-full bg-[#FF4800]"
            @click="handlePopup">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
              <path
                d="M9.99999 8.82153L14.125 4.69653L15.3033 5.87487L11.1783 9.99987L15.3033 14.1249L14.125 15.3032L9.99999 11.1782L5.87499 15.3032L4.69666 14.1249L8.82166 9.99987L4.69666 5.87487L5.87499 4.69653L9.99999 8.82153Z"
                fill="white" />
            </svg>
          </button>
          <h2 class="text-[42px] leading-[48px] text-white mb-[20px]">Coming soon</h2>
          <button class="bg-[#FF4800] rounded-full text-white p-[10px] w-full text-[24px] leading-[32px]"
            @click="handlePopup">Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue"

const showMenu = ref(false)
const showPopup = ref(false)

const handlePopup = () => {
  showPopup.value = !showPopup.value
}
const handleShowMenu = () => {
  showMenu.value = !showMenu.value
}

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
  }
  if (showMenu.value) {
    handleShowMenu();
  }
}
// const showH = ref(false)
const scrollY = ref(0);
const previousScrollY = ref(0);
const currentScroll = ref(0);
const showHeader = ref(true); // Initially show the header

const onScroll = () => {
  currentScroll.value = window.scrollY || document.documentElement.scrollTop;
  console.log('currentVal: ' + currentScroll.value);
  console.log('preVal: ' + previousScrollY.value);

  if (currentScroll.value > previousScrollY.value) {
    // Cuộn xuống, ẩn header
    showHeader.value = false;
  } else {
    showHeader.value = true;
  }
  if (currentScroll.value === 0) {
    showHeader.value = false;
  }
  previousScrollY.value = currentScroll.value <= 0 ? 0 : currentScroll.value;
};
onMounted(() => {
  window.addEventListener('scroll', onScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll);
});


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

.bg-opacity {
  background-color: rgba(0, 0, 0, 0.25);
  backdrop-filter: blur(8px);
  opacity: 0;
  transition: all 0.3s ease-in-out;
}

.showPopup {
  display: flex;
  opacity: 1;
  transition: all 0.3s ease-in-out;
}

.popup {
  animation: hiddenPopup 0.3s 1 ease-in-out backwards;
}

.popupShow {
  animation: showPopup 0.3s 1 ease-in-out backwards;
}

@keyframes showPopup {
  0% {
    transform: translateY(-30px);
    opacity: 0;
  }

  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes hiddenPopup {
  0% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

.sticky-header {
  transition: all 0.3s ease-in-out;
  display: block;
  height: 0;
  opacity: 0;
  position: fixed;
  top: 0;
}

.showH {
  opacity: 1 !important;
}
</style>
