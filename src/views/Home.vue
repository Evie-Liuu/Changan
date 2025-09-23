<template>
  <main
    class="h-screen w-screeen relative flex flex-col justify-center items-center lg:flex-none bg-[url('@/assets/images/Web_v2_N_Bcakground.webp')] bg-cover bg-center overflow-hidden lg:bg-[url('@/assets/images/Backgound_v2_N_Hemei.webp')]"
  >
    <!-- School Title -->
    <section class="lg:absolute lg:top-8 lg:left-8">
      <div>彰化縣</div>
      <div>長安</div>
      <div>國小</div>
    </section>
    <!-- Cover -->
    <section class="">
      <div
        :class="[
          'transition-all duration-3000 ease-out',
          isLoaded ? 'opacity-100' : 'opacity-0',
        ]"
        class="lg:w-220 lg:h-full flex items-center justify-center lg:justify-start"
      >
        <img
          :src="IceCreamMelting"
          class="pointer-events-none select-none"
          alt="Hemei_cover"
        />
        <!-- <img
          :src="IceCreamMelting_mobile"
          class="block lg:hidden pointer-events-none select-none"
          alt="Hemei_cover"
        /> -->
      </div>
    </section>
    <!-- Menu Buttons -->
    <section class="h-full flex items-center lg:items-end justify-center">
      <div
        :class="[
          'transition-all duration-3000 ease-out',
          isLoaded ? 'opacity-100' : 'opacity-0',
        ]"
        class="flex flex-col lg:flex-row lg:gap-5 items-center justify-center text-xl lg:text-2xl lg:pb-25"
      >
        <router-link
          to="/about"
          class="relative"
          @mouseover="hoveredIndex = 0"
          @mouseleave="hoveredIndex = null"
        >
          <img
            :src="hoveredIndex === 0 ? button1Selected : button1Unselected"
            class="pointer-events-none select-none w-52 lg:w-auto"
            alt="Button_1"
          />
          <span
            class="absolute inset-0 flex items-center justify-center text-white ps-5 tracking-widest"
            >校園探索</span
          >
        </router-link>
        <router-link
          to="/actions"
          class="relative"
          @mouseover="hoveredIndex = 1"
          @mouseleave="hoveredIndex = null"
          ><img
            :src="hoveredIndex === 1 ? button2Selected : button2Unselected"
            class="pointer-events-none select-none w-52 lg:w-auto"
            alt="Button_2"
          />
          <span
            class="absolute inset-0 flex items-center justify-center text-white ps-5 tracking-widest"
            >SDGs行動</span
          ></router-link
        >
        <router-link
          to="/sdgs"
          class="relative -translate-x-1/6"
          @mouseover="hoveredIndex = 2"
          @mouseleave="hoveredIndex = null"
          ><img
            :src="hoveredIndex === 2 ? button3Selected : button3Unselected"
            class="pointer-events-none select-none w-52 lg:w-auto"
            alt="Button_3"
          />
          <span
            class="absolute inset-0 flex items-center justify-center text-white ps-5 tracking-widest"
            >SDGs成果</span
          ></router-link
        >
      </div>
    </section>
  </main>
</template>
<script setup>
import { ref, onMounted } from "vue";
import IceCreamMelting from "@/assets/images/ice_cream_community.png";
import button1Unselected from "@/assets/images/Paint_1_v2_Unselected.png";
import button1Selected from "@/assets/images/Paint_1_v2_Selected.png";
import button2Unselected from "@/assets/images/Paint_2_v2_Unselected.png";
import button2Selected from "@/assets/images/Paint_2_v2_Selected.png";
import button3Unselected from "@/assets/images/Paint_3_v2_Unselected.png";
import button3Selected from "@/assets/images/Paint_3_v2_Selected.png";

const hoveredIndex = ref(null);
const isLoaded = ref(false);

onMounted(() => {
  setTimeout(() => {
    isLoaded.value = true;
  }, 100);
});
</script>
<style scoped>
</style>
