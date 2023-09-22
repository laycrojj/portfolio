<script setup lang="ts">

import { onMounted, onUnmounted, ref } from 'vue';
import BaseIcon from './BaseIcon.vue'; 

const jobs = ["Developer", "Dad", "3D Artist", "Post Graduate"];

const currentJob = ref(jobs[1]);

function iterateJobs(): void {
  let nextIndex = (jobs.indexOf(currentJob.value) + 1) % jobs.length;
  currentJob.value = jobs[nextIndex];
}

let loopJobs: number;
onMounted(() => {

  loopJobs = setInterval(iterateJobs, 2000);

});

onUnmounted(() => clearInterval(loopJobs));




</script>

<template>
  <div class="p-8 w-full min-h-screen md:flex md:gap-4 md:items-center">
    <div class=" pt-20 basis-3/5 order-last">
      <h1 id="title-text" class="text-yellow-50 font-bold h-96 text-6xl font-sans leading-relaxed md:text-8xl">I'm Owen Jackson:<br><span class="italic text-yellow-400">{{ currentJob }}</span></h1>
    </div>
    <div class="basis-2/5 max-h-max">
      <BaseIcon :name="currentJob"></BaseIcon>
    </div>
  </div>
</template>

<!-- <style>
@keyframes cursor-blink {
  0% {
    opacity: 0;
  }
}

#title-text::after {
  content: "";
  position: relative;
  left: 20px;
  top: 10px;
  width: 8px;
  height: 100%;
  background: rgb(250, 204, 21);
  display: inline-block;
  animation: cursor-blink 1s steps(2) infinite;
}
</style> -->
