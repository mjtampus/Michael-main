<template>
  <main class="py-2 mx-4 my-10 md:mx-12 lg:mx-32 xl:mx-32">
    <div class="block lg:flex xl:flex">
      <!-- Left Section with Text Content -->
      <section class="w-full lg:w-1/2 xl:w-2/3 md:text-center lg:text-left xl:text-left mt-0 lg:mt-12 md:mt-12 xl:mt-32">
        <h2 class="mb-4 text-4xl font-bold md:text-6xl">Welcome to my Portfolio! </h2>
        <p class="mb-4 text-lg text-gray-700">I'm Michael John B. Tampus , a dedicated and passionate web developer committed to crafting immersive and user-friendly web experiences. With a keen eye for design and a love for innovative technology, I strive to create digital solutions that captivate audiences and elevate online interactions.</p>
        <p class="mb-4 text-lg text-gray-700">As a web developer, I am driven by a deep-seated passion for creativity and problem-solving. Each project I undertake is an opportunity to blend artistry with functionality, transforming ideas into dynamic and engaging web environments. Whether it's building sleek and intuitive user interfaces or optimizing backend functionality for seamless performance, I approach every task with meticulous attention to detail and a relentless pursuit of excellence.</p>
        <p class="mb-4 text-lg text-gray-700">In today's fast-paced digital landscape, the need for exceptional web experiences has never been greater. Whether it's a sleek corporate website, an interactive e-commerce platform, or a dynamic web application, I am committed to helping businesses and individuals alike stand out in the crowded online space. With a blend of creativity, technical expertise, and a relentless pursuit of perfection, I am ready to turn your digital dreams into reality.</p>
        <div class="w-full flex justify-right md:justify-center lg:justify-start xl:justify-start">
          <a href="#" class="mr-5 items-center rounded-md bg-black px-6 py-3 font-semibold text-white md:mr-6 lg:mr-8">Contact me</a>
          <a href="#" class="flex max-w-full items-center font-bold bg-gray-900/10 active:bg-gray-900/20 rounded-lg py-3 px-3">
            <img src="https://assets.website-files.com/6458c625291a94a195e6cf3a/6458c625291a94bd85e6cf98_ArrowUpRight%20(4).svg" alt="" class="mr-2 inline-block max-h-4 w-5" />
            <p>Download CV</p>
          </a>
        </div>
      </section>

      <!-- Right Section with Image Stack -->
      <section class="flex justify-center md:justify-center lg:justify-end xl:justify-end text-center w-full lg:w-1/2 xl:w-1/2 border border-gray-200 my-5 rounded order-first lg:order-none xl:order-none lg:ml-6 xl:ml-6">
        <div class="relative w-80 lg:w-full xl:w-full">
          <!-- Image Stack -->
          <transition name="fade" mode="out-in">
            <img :key="currentIndex" :src="currentImageUrl" :alt="'Image ' + (currentIndex + 1)" class="w-full object-cover rounded-lg shadow-lg">
          </transition>

          <!-- Navigation Buttons -->
          <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex space-x-4">
            <button @click="prevImage" class="px-3 py-1 text-white bg-gray-800 rounded">Prev</button>
            <button @click="nextImage" class="px-3 py-1 text-white bg-gray-800 rounded">Next</button>
          </div>
        </div>
      </section>
    </div>
  </main>
</template>

<script setup>
import { ref, computed } from 'vue';

const images = [
  '/src/views/assets/Image5.jpg',
  '/src/views/assets/image2.jpg',
  '/src/views/assets/image4.jpg'
];

const currentIndex = ref(0);

const currentImageUrl = computed(() => {
  return images[currentIndex.value];
});

const nextImage = () => {
  currentIndex.value = (currentIndex.value + 1) % images.length;
};

const prevImage = () => {
  currentIndex.value = (currentIndex.value - 1 + images.length) % images.length;
};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
