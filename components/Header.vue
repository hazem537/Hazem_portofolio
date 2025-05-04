<template>
  <header
    class="w-[90%] h-16 fixed top-0 left-[5%] mx-auto rounded-b-xl z-50 bg-[#1B1B1B]/80 backdrop-blur-md text-white shadow-lg transition-all duration-300"
  >
    <nav class="flex justify-around items-center h-full w-full p-2">
      <div class="flex items-center gap-8">
        <NuxtLink
          to="/#Hero"
          class="nav-link group"
          :class="{ active_link: $route.hash === '#Hero' }"
        >
          <span class="nav-text">Home</span>
        </NuxtLink>

        <NuxtLink
          to="/#Work"
          class="nav-link group"
          :class="{ active_link: $route.hash === '#Work' }"
        >
          <span class="nav-text">Works</span>
        </NuxtLink>

        <NuxtLink
          to="/#AboutMe"
          class="nav-link group"
          :class="{ active_link: $route.hash === '#AboutMe' }"
        >
          <span class="nav-text">About Me</span>
        </NuxtLink>
      </div>

      <div class="flex items-center gap-5">
        <a
          href="https://www.linkedin.com/in/hazem-hamdy-238533324/"
          target="_blank"
          class="social-link group"
        >
          <div class="social-icon-wrapper">
            <img
              src="~ assets/images/whitelinkedin.png"
              class="social-icon"
              alt="LinkedIn"
            />
          </div>
        </a>
        <a 
          href="https://github.com/hazem537" 
          target="_blank"
          class="social-link group"
        >
          <div class="social-icon-wrapper">
            <img
              src="~ assets/images/whitegithub.png"
              class="social-icon"
              alt="GitHub"
            />
          </div>
        </a>
      </div>
    </nav>
  </header>
</template>

<script lang="ts" setup>
// Add scroll event listener to change header style on scroll
onMounted(() => {
  window.addEventListener('scroll', () => {
    const header = document.querySelector('header')
    if (window.scrollY > 50) {
      header?.classList.add('scrolled')
    } else {
      header?.classList.remove('scrolled')
    }
  })
})
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cairo:wght@200..1000&family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&display=swap");

nav {
  font-family: "IBM Plex Mono", monospace;
  @apply md:text-[1rem] text-[.7rem] text-[#9C9C9C];
}

.nav-link {
  @apply relative px-2 py-1 transition-all duration-300;
}

.nav-text {
  @apply relative z-10;
}

.nav-link::before {
  content: '';
  @apply absolute inset-0 bg-[#62BA1B] opacity-0 rounded-md transition-opacity duration-300;
  transform: scale(0.8);
}

.nav-link:hover::before {
  @apply opacity-10;
  transform: scale(1);
}

.active_link {
  @apply text-[#62BA1B];
}

.active_link::after {
  content: '';
  @apply absolute bottom-0 left-0 w-full h-0.5 bg-[#62BA1B] transform scale-x-100 transition-transform duration-300;
}

.nav-link:not(.active_link)::after {
  content: '';
  @apply absolute bottom-0 left-0 w-full h-0.5 bg-[#62BA1B] transform scale-x-0 transition-transform duration-300;
}

.nav-link:hover::after {
  @apply scale-x-100;
}

.social-link {
  @apply relative transition-transform duration-300 hover:scale-110;
}

.social-icon-wrapper {
  @apply relative overflow-hidden rounded-full transition-all duration-300;
}

.social-icon {
  @apply w-8 h-8 transition-transform duration-300;
}

.social-link:hover .social-icon {
  @apply transform scale-110;
}

.social-icon-wrapper::before {
  content: '';
  @apply absolute inset-0 bg-[#62BA1B] opacity-0 transition-opacity duration-300;
}

.social-link:hover .social-icon-wrapper::before {
  @apply opacity-20;
}

/* Scroll effect */
header.scrolled {
  @apply bg-[#1B1B1B]/90 shadow-xl;
  transform: translateY(-2px);
}

/* Animation for initial load */
@keyframes slideDown {
  from {
    transform: translateY(-100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

header {
  animation: slideDown 0.5s ease-out forwards;
}
</style>
