<script setup lang="ts">

import { ref } from 'vue';

const props = defineProps({
    activeSection: String
});

const menuVisible = ref(false);

</script>

<template>

    <nav class="fixed w-full z-20 top-0 left-0 bg-zinc-900 border-b-2 border-yellow-400">
        <div class="flex flex-wrap mx-12 items-center justify-between p-4">
                <span class="text-2xl font-semibold text-white">Owen Jackson</span>
            <div class="">
                <button @click="menuVisible=!menuVisible" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-sticky" aria-expanded="false">
                    <span class="sr-only">Open main menu</span>
                    <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
                    </svg>
                </button>
            </div>
            <div :class="{ hidden: !menuVisible }" class="items-center justify-between w-full md:flex md:w-auto md:order-1">
                <ul class="flex flex-col p-4 md:p-0 mt-4 font-bold border md:flex-row md:space-x-8 md:mt-0 md:border-0 border-gray-700 rounded-lg">
                    <li>
                        <a href="#welcome" class="block py-2 pl-3 pr-4 text-white bg-blue-700 rounded md:bg-transparent md:p-0"
                        :class="{'text-yellow-300':activeSection=='welcome'}">Home</a>
                    </li>
                    <li>
                        <a href="#about" class="block py-2 pl-3 pr-4 rounded md:hover:bg-transparent md:hover:text-blue-700 md:p-0 hover:text-blue-500 text-white hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent border-gray-700"
                        :class="{'text-yellow-300':activeSection=='about'}">About</a>
                    </li> 
                    <li> 
                        <a href="#work" class="block py-2 pl-3 pr-4 rounded md:hover:bg-transparent md:hover:text-blue-700 md:p-0 hover:text-blue-500 text-white hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent border-gray-700"
                        :class="{'text-yellow-300':activeSection=='work'}" >Work</a>
                    </li> 
                    <li> 
                        <a href="#contact" class="block py-2 pl-3 pr-4 rounded md:hover:bg-transparent md:hover:text-blue-700 md:p-0 hover:text-blue-500 text-white hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent border-gray-700"
                        :class="{'text-yellow-300':activeSection=='contact'}">Contact</a>
                    </li> 
                </ul>
            </div>
        </div>
    </nav>
  
        </template>