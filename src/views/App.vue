<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'

const isMenuOpen = ref(false);

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
  <header>
      <nav>
        <nav class="block w-full py-2 px-4 md:px-12 lg:px-32 xl:px-32 text-gray-500 bg-purple-700 shadow-md">
          <div class="container flex items-center justify-between mx-auto text-white">
            <a href="#" class="mr-4 block cursor-pointer py-1.5 font-sans text-xl font-medium leading-relaxed">
              <img src="./assets/Logo.png" class="h-12 w-12"/>
              <p class="ml-2">Michael Projects</p>
            </a>
            <div class="hidden lg:block">
              <ul class="flex flex-col gap-2 mt-2 mb-4 lg:mb-0 lg:mt-0 lg:flex-row lg:items-center lg:gap-6">
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/">Home</RouterLink>
                  </a>
                </li>
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/about">About</RouterLink>
                  </a>
                </li>
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/project">Services</RouterLink>
                  </a>
                </li>
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/contact">Contact</RouterLink>
                  </a>
                </li>
              </ul>
            </div>
           
            <button @click="toggleMenu" class="relative ml-auto h-6 max-h-[40px] w-6 max-w-[40px] select-none rounded-lg text-center align-middle font-sans text-xs font-medium uppercase text-white transition-all hover:bg-transparent focus:bg-transparent active:bg-transparent disabled:pointer-events-none disabled:opacity-50 disabled:shadow-none lg:hidden" type="button">
              <span class="absolute transform -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16"></path>
                </svg>
              </span>
            </button>
          </div>

          <div class="lg:hidden" v-show="isMenuOpen" @click.away="isMenuOpen = false">
              <ul class="flex flex-col gap-2 mt-2 mb-4 lg:mb-0 lg:mt-0 lg:flex-row lg:items-center lg:gap-6">
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/">Home</RouterLink>
                  </a>
                </li>
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/about">About</RouterLink>
                  </a>
                </li>
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/project">Services</RouterLink>
                  </a>
                </li>
                <li class="flex items-center p-1 font-sans text-sm font-medium leading-normal">
                  <a class="flex items-center text-white hover:text-gray-200">
                    <RouterLink to="/contact">Contact</RouterLink>
                  </a>
                </li>
              </ul>
            </div>
        </nav> 
      </nav>
  </header>

  <RouterView/>
</template>
