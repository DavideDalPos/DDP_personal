<template>
  <div class="w-full h-full absolute">
    <div class="relative overflow-hidden h-full">
      <img
        :src="slide.img"
        class="w-screen absolute object-cover h-full -z-10"
      />

      <div class="absolute w-full h-full bg-black bg-opacity-65 -z-10" />
      <div class="container mx-auto px-8 z-20 h-full relative flex items-end">
        <div class="prose max-w-max md:max-w-5xl bottom-4 py-12">
          <h1 class="text-white">{{ slide.title }}</h1>
          <div
            class="text-white my-8 text-lg max-w"
            v-html="slide.description"
          />
          <NuxtLink
            class="bg-green-600 text-white px-4 py-2 no-underline"
            :to="slide.link.href"
          >
            {{ slide.link.label }}
          </NuxtLink>
        </div>
      </div>
      <div
        v-if="slide.copyright"
        class="bottom-4 right-4 text-white absolute opacity-75"
      >
        {{ slide.copyright }}
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  slide: {
    type: Object,
    required: true
  }
})
</script>
