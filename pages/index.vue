<template>
  <div class="flex min-h-screen flex-col">
    <Hero />
    <Work />
    <AboutMe />
    <Footer />
  </div>
</template>

<script lang="ts" setup>
useHead({
  title: 'Hazem Hamdy | Frontend Developer',
  meta: [
    {
      name: 'description',
      content:
        'Portfolio of Hazem Hamdy — Frontend Developer specializing in Nuxt.js, Vue.js, React, and modern web technologies.',
    },
  ],
  link: [
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&family=Raleway:ital,wght@0,100..900;1,100..900&display=swap',
    },
  ],
})
</script>

<style>
* {
  font-family: "IBM Plex Mono", monospace;
}

html {
  scroll-behavior: smooth;
}

body {
  @apply bg-[#080808] text-[#9C9C9C];
}
</style>
