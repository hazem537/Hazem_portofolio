<template>
  <div class="flex flex-col h-full snap-y snap-mandatory">
    <Hero class="min-h-screen"></Hero>
    <Work class="min-h-screen"></Work>
    <AboutMe class="min-h-screen"></AboutMe>
    <Footer> </Footer>
  </div>
</template>

<script lang="ts" setup>
const router = useRouter();
router.push("/#Hero");
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cairo:wght@200..1000&family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&family=Raleway:ital,wght@0,100..900;1,100..900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Cairo:wght@200..1000&family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&display=swap");
* {
  font-family: "IBM Plex Mono", monospace;
  @apply text-[#9C9C9C];
}
html {
  scroll-behavior: smooth;
}
</style>
