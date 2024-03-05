<template>
  <div class="bg-primary" id="whitepaper">
    <div class="pt-[32px] pb-[12px] gap-[24px] container flex flex-col min-[1200px]:pb-[24px] min-[1200px]:pt-[48px]">
      <div class="flex justify-between">
        <a href=""><img class="h-[48px]" src="../assets/images/Logo.svg" alt=""></a>
        <button class="cursor-pointer hover:opacity-[0.7] ease-linear duration-300" id="back-to-top">
          <img class="h-[48px]"
               src="../assets/images/btn-go-top.png"
               alt="">
        </button>
      </div>
      <h3 class="text-[24px] leading-[32px] font-[900] text-white min-[992px]:text-[72px] min-[992px]:leading-[90px]">Be
        a part of the LION Community</h3>
      <p class="text-[14px] leading-[24px] text-white font-[300] min-[992px]:text-[18px] min-[992px]:leading-[30px]">
        The LION community is built on caring for one another, promoting kindness, educating people about
        cryptocurrency, fundraising, having a blast, creating memes, and embracing the absurd. Engage with our awesome
        community through the links below
      </p>
      <div class="border-b w-full border-[#1E293B]"></div>
      <div class="flex justify-between items-center">
        <div class="flex gap-[12px] items-center">
          <a
              class="cursor-pointer  rounded-[2px] overflow-hidden max-[375px]:w-[25px] max-[375px]:h-[25px]
                hover:opacity-[0.7] ease-linear duration-300  min-[375px]:w-[38px] min-[375px]:h-[38px] "
              href="https://twitter.com/kingofmeme_lion"
              target="_blank"
          >
            <img src="../assets/images/x.png" alt="">
          </a>
          <a
              class="cursor-pointer  rounded-[2px] overflow-hidden max-[375px]:w-[25px] max-[375px]:h-[25px]
                hover:opacity-[0.7] ease-linear duration-300  min-[375px]:w-[38px] min-[375px]:h-[38px] "
              href="https://t.me/kingofmeme_Announcement"
              target="_blank"
          >
            <img src="../assets/images/tele.png" alt="">
          </a>
          <a
              class="cursor-pointer  rounded-[2px] overflow-hidden max-[375px]:w-[25px] max-[375px]:h-[25px]
                hover:opacity-[0.7] ease-linear duration-300  min-[375px]:w-[38px] min-[375px]:h-[38px] "
              href="https://www.facebook.com/kingofmeme.lion"
              target="_blank"
          >
            <img
                class=""
                src="../assets/images/fb.png"
                alt="">
          </a>
        </div>
        <span class="text-[14px] text-white font-[300] leading-[24px] max-[375px]:w-[50px]:text-[10px]">© All rights reserved by Lion.meme</span>
      </div>
    </div>
  </div>
</template>

<script setup>
document.addEventListener('DOMContentLoaded', function () {
  const backToTopBtn = document.getElementById('back-to-top'); // Assuming you have an element with this ID

  if (backToTopBtn) { // Check if the element exists
    window.addEventListener('scroll', () => {
      if (window.scrollY > 100) {
        backToTopBtn.classList.add('show');
      } else {
        backToTopBtn.classList.remove('show');
      }
    });

    backToTopBtn.addEventListener('click', () => {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    });
  }
});

</script>

<style lang="css" scoped>
.bg-primary {
  background-color: #0F172A;
}
</style>