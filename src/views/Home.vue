<template>
  <main
    class="h-screen w-screeen relative flex flex-col justify-center items-center lg:flex-none bg-[url('@/assets/images/Mobile/Mobile_Background.png')] bg-cover bg-center overflow-hidden lg:bg-[url('@/assets/images/Web_Background.png')]"
  >
    <!-- School Title -->
    <section class="lg:absolute lg:-top-2 lg:right-10">
      <img
        src="@/assets/images/ChangAn_Logo.png"
        class="hidden lg:block pointer-events-none select-none w-35"
        alt="Changan_logo"
      />
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
          alt="Changan_cover"
        />
        <!-- <img
          :src="IceCreamMelting_mobile"
          class="block lg:hidden pointer-events-none select-none"
          alt="Changan_cover"
        /> -->
      </div>
    </section>
    <!-- School Title -->
    <section class="">
      <div
        :class="[
          'transition-all duration-3000 ease-out',
          isLoaded ? 'opacity-100' : 'opacity-0',
        ]"
        class="lg:w-220 lg:h-full flex items-center justify-center lg:justify-start"
      >
        <img
          src="@/assets/images/ChangAn_School_title.png"
          class="pointer-events-none select-none"
          alt="Changan_cover"
        />
      </div>
    </section>
    <!-- Menu Buttons -->
    <section
      class="h-full flex items-center lg:items-end justify-center font-bold text-green-dark"
    >
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
            :src="hoveredIndex === 0 ? button1Selected : buttonUnselected"
            class="pointer-events-none select-none w-52 lg:w-60"
            alt="Button_1"
          />
          <span
            class="absolute inset-0 flex items-center justify-center ps-5 tracking-widest"
            >校園探索</span
          >
        </router-link>
        <router-link
          to="/actions"
          class="relative"
          @mouseover="hoveredIndex = 1"
          @mouseleave="hoveredIndex = null"
          ><img
            :src="hoveredIndex === 1 ? button2Selected : buttonUnselected"
            class="pointer-events-none select-none w-52 lg:w-60"
            alt="Button_2"
          />
          <span
            class="absolute inset-0 flex items-center justify-center ps-5 tracking-widest"
            >SDGs行動</span
          ></router-link
        >
        <router-link
          to="/sdgs"
          class="relative -translate-x-1/6"
          @mouseover="hoveredIndex = 2"
          @mouseleave="hoveredIndex = null"
          ><img
            :src="hoveredIndex === 2 ? button3Selected : buttonUnselected"
            class="pointer-events-none select-none w-52 lg:w-60"
            alt="Button_3"
          />
          <span
            class="absolute inset-0 flex items-center justify-center ps-5 tracking-widest"
            >SDGs成果</span
          ></router-link
        >
      </div>
    </section>
  </main>
</template>
<script setup>
import { ref, onMounted } from "vue";
import IceCreamMelting from "@/assets/images/Earth_IceCream.webp";
import buttonUnselected from "@/assets/images/Bar_Unselected.png";
import button1Selected from "@/assets/images/Bar_Selected_School.png";
import button2Selected from "@/assets/images/Bar_Selected_Action.png";
import button3Selected from "@/assets/images/Bar_Selected_Result.png";

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
