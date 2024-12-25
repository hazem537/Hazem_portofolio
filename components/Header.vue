<template>
  <header
    class="w-[90%] h-16 fixed top-0 left-[5%] mx-auto rounded-b-xl z-10 bg-[#1B1B1B] text-white"
  >
    <nav class="flex justify-around items-center h-full w-full p-2">
      <NuxtLink
        to="/#Hero"
        class="transation-all duration-100"
        :class="{ active_link: $route.hash === '#Hero' }"
      >
        <h2>Home</h2>
      </NuxtLink>

      <NuxtLink
        to="/#Work"
        class="transation-all duration-100"
        :class="{ active_link: $route.hash === '#Work' }"
      >
        <p>works</p>
      </NuxtLink>
      <NuxtLink
        to="/#AboutMe"
        class="transation-all duration-100"
        :class="{ active_link: $route.hash === '#AboutMe' }"
      >
        <p>About Me</p>
      </NuxtLink>
      <div class="flex items-cenetr gap-5">
        <a
          href="https://www.linkedin.com/in/hazem-hamdy-238533324/"
          target="_blank"
        >
          <img
            src="~ assets/images/whitelinkedin.png"
            class="rounded-full w-8 h-8"
        /></a>
        <a href="https://github.com/hazem537" target="_blank">
          <img
            src="~ assets/images/whitegithub.png"
            class="rounded-full w-8 h-8"
        /></a>

        <!-- <p>{{ x   }} - {{ y  }}</p> -->
      </div>
    </nav>
  </header>
</template>

<script lang="ts" setup></script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cairo:wght@200..1000&family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&display=swap");
nav {
  font-family: "IBM Plex Mono", monospace;
  @apply md:text-[1rem] text-[.7rem] text-[#9C9C9C];
}
.active_link {
  @apply border-b border-green-500;
}
</style>
