<script setup lang="ts">
const title = "see you soon";
const { data: home } = await useAsyncData(() => queryCollection("content").path("/").first());
</script>

<template>
  <div class="relative h-screen w-full overflow-hidden flex">
    <NuxtImg src="background.png" class="absolute inset-0 w-full h-full object-cover -z-10" format="webp" />
    <div class="h-screen md:w-3/6 lg:w-[340px] p-[26px] bg-linear-to-b from-neutral-500 to-transparent">
      <h1 class="font-questrial text-[72px] leading-[1.2] text-primary uppercase">{{ title }}</h1>
    </div>
    <div class="flex items-center justify-center">
      <ContentRenderer v-if="home" :value="home" class="w-1/3 font-questrial" />
    </div>
  </div>
</template>
