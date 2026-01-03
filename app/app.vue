<script setup lang="ts">
const title = "see you soon";
const { data: home } = await useAsyncData(() => queryCollection("content").path("/").first());
</script>

<template>
  <div class="relative h-screen w-full overflow-hidden flex flex-col lg:flex-row justify-between">
    <NuxtImg src="background.png" class="absolute inset-0 w-full h-full object-cover object-top -z-10" format="webp" />
    <div
      class="h-[250px] md::h-screen w-full lg:w-3/6 lg:w-[340px] p-[26px] bg-linear-to-b from-neutral-500 to-transparent"
    >
      <h1 class="font-questrial text-[64px] md:text-[96px] leading-[1.2] text-primary uppercase">{{ title }}</h1>
    </div>
    <div class="flex items-center justify-center">
      <ContentRenderer
        v-if="home"
        :value="home"
        class="md:w-full lg:w-2/3 xl:w-1/3 font-questrial text-white text-xl p-[26px] [&_strong]:text-2xl bg-neutral-500/50 md:bg-neutral-500/25 border-4 border-primary"
      />
    </div>
  </div>
</template>
