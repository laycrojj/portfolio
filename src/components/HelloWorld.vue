<script setup lang="ts">

import { onMounted, onUnmounted, ref } from 'vue';

const jobs = ["Developer", "Dad", "3D Artist", "Tinkerer", "Team Leader"];

const currentJob = ref(jobs[1]);

function iterateJobs(): void {
  let nextIndex = (jobs.indexOf(currentJob.value) + 1) % jobs.length;
  currentJob.value = jobs[nextIndex];
}

let loopJobs;
onMounted(() => {

  loopJobs = setInterval(iterateJobs, 2000);

});

onUnmounted(() => clearInterval(loopJobs));




</script>

<template>
  <div class="p-20 w-4/6">
    <div>
      <h1 id="title-text" class="text-yellow-50 font-bold text-8xl font-sans leading-relaxed h-24">I'm Owen Jackson,<br><span class="italic text-yellow-400">{{ currentJob }}</span></h1>
      <!-- <div class="h-4 w-full bg-yellow-400 mt-5"></div> -->
    </div>
  </div>
</template>

<style>
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
</style>
