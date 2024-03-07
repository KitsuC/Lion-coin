<template>
  <header-component/>
  <div>
    <home-view/>
  </div>
  <footer-component/>
</template>

<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import HomeView from "../view/HomeView.vue";
import FooterComponent from "../components/FooterComponent.vue";
import {watch, ref} from "vue";
import axios from "axios";

import lion from '../assets/images/Lionbaner.png';
import vectorWhite from '../assets/images/vector-white.png';
import coin1 from '../assets/images/coin-1.png';
import coin2 from '../assets/images/coin-2.png';
import coin3 from '../assets/images/coin-3.png';
import coin4 from '../assets/images/coin-4.png';
import coin5 from '../assets/images/coin-5.png';
import coin6 from '../assets/images/coin-6.png';
import coin7 from '../assets/images/coin-7.png';
import coin8 from '../assets/images/coin-8.png';
import monkeyHoverCoin from '../assets/images/monkey-hover-coin.jpg';
import lionHunt from '../assets/images/lion-hunt.png';
import wallet1 from '../assets/images/wallet1.png';
import wallet2 from '../assets/images/wallet2.png';
import wallet3 from '../assets/images/wallet3.png';
import wallet4 from '../assets/images/wallet4.png';
import ETH from '../assets/images/ETH.png';
import walletUniswap from '../assets/images/wallet-uniswap.png';
import lionCoin from '../assets/images/lion-coin.png';
import lionRelax from '../assets/images/lion-relax.png';
import meerkat from '../assets/images/meerkat.png';
import coinMoon from '../assets/images/coin-moon.png';
import bird from '../assets/images/bird.png';
import roadmap1 from '../assets/images/roadmap-1.png';
import roadmap2 from '../assets/images/roadmap-2.png';
import roadmap3 from '../assets/images/roadmap-3.png';
import roadmap4 from '../assets/images/roadmap-4.png';

const dataArray = ref([
  lion,
  vectorWhite,
  coin1,
  coin2,
  coin3,
  coin4,
  coin5,
  coin6,
  coin7,
  coin8,
  monkeyHoverCoin,
  lionHunt,
  wallet1,
  wallet2,
  wallet3,
  wallet4,
  ETH,
  walletUniswap,
  lionCoin,
  lionRelax,
  meerkat,
  coinMoon,
  bird,
  roadmap1,
  roadmap2,
  roadmap3,
  roadmap4
]);
const fetchedImages = ref([]);
const asyncFcn = async () => {
  const imageChunks = chunkArray(dataArray.value, 3);
  for (const imageRow of imageChunks) {
    const responses = await Promise.all(imageRow.map(path => axios.get(path, { responseType: 'blob' })));

    fetchedImages.value.push(...responses.map(response => ({
      data: URL.createObjectURL(response.data),
      originalPath: response.config.url
    })));
  }
}
function chunkArray(array, size) {
  const result = [];
  for (let i = 0; i < array.length; i += size) {
    result.push(array.slice(i, i + size));
  }
  return result;
}
await asyncFcn();

</script>

