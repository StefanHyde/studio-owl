<script setup lang="ts">
useHead({
  title: "Développé par Stefan H",
  meta: [
    {
      name: "description",
      content:
        "Site vitrine, e-commerce, ou application web ? Je serais prochainement de retour pour propulser votre activité en ligne",
    },
  ],
});
const { data: home } = await useAsyncData(() => queryCollection("content").path("/").first());
</script>

<template>
  <div class="relative h-screen w-full overflow-hidden flex flex-col lg:flex-row">
    <NuxtImg
      src="background.png"
      class="absolute inset-0 w-full h-full object-cover object-[25%_25%] -z-10"
      format="webp"
    />
    <div
      class="h-[360px] md:h-screen w-full lg:w-3/6 lg:w-[340px] p-[26px] bg-linear-to-b from-neutral-500 to-transparent flex items-center"
    >
      <h1 class="font-poppins text-[64px] md:text-[96px] font-semibold leading-[1.2] text-primary uppercase w-1/2">
        See you <span class="text-secondary">soon</span>
      </h1>
    </div>
    <div class="flex items-center justify-center">
      <ContentRenderer
        v-if="home"
        :value="home"
        class="md:w-full lg:w-2/3 xl:w-1/3 font-poppins text-white text-l p-[26px] [&_strong]:text-xl bg-neutral-500/50 md:bg-neutral-500/25 border-4 border-primary"
      />
    </div>
  </div>
</template>
