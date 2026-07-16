<template>
  <header
    class="fixed left-1/2 top-0 z-50 w-[92%] max-w-5xl -translate-x-1/2 rounded-b-2xl border border-[#62BA1B]/10 bg-[#1B1B1B]/80 text-white shadow-lg backdrop-blur-md transition-all duration-300"
    :class="{ scrolled: isScrolled }"
  >
    <nav class="flex h-16 items-center justify-between gap-3 px-4 md:px-6">
      <div class="flex items-center gap-2 sm:gap-4 md:gap-8">
        <NuxtLink
          v-for="link in navLinks"
          :key="link.hash"
          :to="`/${link.hash}`"
          class="nav-link group"
          :class="{ active_link: route.hash === link.hash }"
        >
          <span class="nav-text">{{ link.label }}</span>
        </NuxtLink>
      </div>

      <div class="flex items-center gap-3">
        <a
          href="https://www.linkedin.com/in/hazem-hamdy-238533324/"
          target="_blank"
          rel="noopener noreferrer"
          class="social-link group"
          aria-label="LinkedIn profile"
        >
          <img
            src="~/assets/images/whitelinkedin.png"
            class="social-icon"
            alt=""
          />
        </a>
        <a
          href="https://github.com/hazem537"
          target="_blank"
          rel="noopener noreferrer"
          class="social-link group"
          aria-label="GitHub profile"
        >
          <img
            src="~/assets/images/whitegithub.png"
            class="social-icon"
            alt=""
          />
        </a>
      </div>
    </nav>
  </header>
</template>

<script lang="ts" setup>
const route = useRoute()
const isScrolled = ref(false)

const navLinks = [
  { label: 'Home', hash: '#Hero' },
  { label: 'Works', hash: '#Work' },
  { label: 'About Me', hash: '#AboutMe' },
]

const onScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  onScroll()
  window.addEventListener('scroll', onScroll, { passive: true })
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<style scoped>
nav {
  font-family: "IBM Plex Mono", monospace;
  @apply text-[0.7rem] text-[#9C9C9C] md:text-[1rem];
}

.nav-link {
  @apply relative px-2 py-1 transition-all duration-300;
}

.nav-text {
  @apply relative z-10;
}

.nav-link::before {
  content: '';
  @apply absolute inset-0 rounded-md bg-[#62BA1B] opacity-0 transition-opacity duration-300;
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
  @apply absolute bottom-0 left-0 h-0.5 w-full scale-x-100 bg-[#62BA1B] transition-transform duration-300;
}

.nav-link:not(.active_link)::after {
  content: '';
  @apply absolute bottom-0 left-0 h-0.5 w-full scale-x-0 bg-[#62BA1B] transition-transform duration-300;
}

.nav-link:hover::after {
  @apply scale-x-100;
}

.social-link {
  @apply relative flex h-9 w-9 items-center justify-center rounded-full border border-[#62BA1B]/20 bg-[#080808]/40 transition-all duration-300 hover:scale-110 hover:border-[#62BA1B]/50;
}

.social-icon {
  @apply h-5 w-5 transition-transform duration-300;
}

.social-link:hover .social-icon {
  transform: scale(1.08);
}

header.scrolled {
  @apply border-[#62BA1B]/20 bg-[#1B1B1B]/95 shadow-xl;
  transform: translate(-50%, -2px);
}

@keyframes slideDown {
  from {
    transform: translate(-50%, -100%);
    opacity: 0;
  }
  to {
    transform: translate(-50%, 0);
    opacity: 1;
  }
}

header {
  animation: slideDown 0.5s ease-out forwards;
}
</style>
