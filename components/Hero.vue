<template>
  <section
    id="Hero"
    class="relative min-h-screen overflow-hidden bg-[#080808] pt-24 pb-16 lg:pt-28 lg:pb-20"
  >
    <div class="pointer-events-none absolute inset-0 overflow-hidden">
      <div
        class="absolute left-10 top-24 h-72 w-72 rounded-full bg-[#62BA1B] opacity-20 blur-3xl mix-blend-multiply animate-blob"
      ></div>
      <div
        class="absolute right-10 top-40 h-72 w-72 rounded-full bg-[#3F8E00] opacity-20 blur-3xl mix-blend-multiply animate-blob animation-delay-2000"
      ></div>
      <div
        class="absolute -bottom-10 left-1/3 h-72 w-72 rounded-full bg-[#62BA1B] opacity-15 blur-3xl mix-blend-multiply animate-blob animation-delay-4000"
      ></div>
    </div>

    <div
      class="relative z-10 mx-auto grid max-w-6xl grid-cols-1 items-center gap-12 px-4 md:px-8 lg:grid-cols-[1.1fr_0.9fr]"
    >
      <div class="flex flex-col items-center gap-8 text-center lg:items-start lg:text-left">
        <div class="space-y-5">
          <span
            class="inline-flex items-center rounded-full border border-[#62BA1B]/40 bg-[#62BA1B]/10 px-4 py-1.5 text-sm font-medium text-[#62BA1B]"
          >
            Hi, my name is
          </span>

          <h1 class="name-gradient text-4xl font-bold leading-tight sm:text-5xl lg:text-7xl">
            Hazem Hamdy
          </h1>

          <h2 class="text-xl text-[#62BA1B] sm:text-2xl lg:text-3xl">
            Frontend Developer
          </h2>

          <p class="max-w-xl text-base leading-relaxed text-gray-300 sm:text-lg">
            Passionate frontend developer specializing in Nuxt.js, Vue.js,
            React, and modern web technologies. I build beautiful, performant
            experiences that feel fast and look polished.
          </p>
        </div>

        <div class="flex flex-wrap items-center justify-center gap-4 lg:justify-start">
          <a
            href="/cv.pdf"
            target="_blank"
            rel="noopener noreferrer"
            class="group relative inline-flex items-center justify-center rounded-xl border border-[#62BA1B] bg-[#3F8E00] px-7 py-3.5 text-sm font-bold text-white transition-all duration-300 hover:scale-105 hover:bg-[#62BA1B] hover:shadow-lg hover:shadow-[#62BA1B]/25"
          >
            <span class="absolute inset-0 z-0 rounded-xl bg-[#3F8E00] opacity-30 blur-xl"></span>
            <span class="relative z-10">Download CV</span>
          </a>
          <a
            href="#Contact"
            class="inline-flex items-center justify-center rounded-xl border border-[#62BA1B] px-7 py-3.5 text-sm font-bold text-white transition-all duration-300 hover:scale-105 hover:bg-[#62BA1B] hover:shadow-lg hover:shadow-[#62BA1B]/25"
          >
            Contact Me
          </a>
        </div>

        <div class="grid w-full max-w-xl grid-cols-3 gap-3">
          <div
            v-for="stat in stats"
            :key="stat.label"
            class="rounded-2xl border border-[#62BA1B]/20 bg-[#1B1B1B]/60 p-4 backdrop-blur-sm transition-all duration-300 hover:border-[#62BA1B]/50 hover:bg-[#1B1B1B]/80"
          >
            <p class="text-2xl font-bold text-white sm:text-3xl">{{ stat.value }}</p>
            <p class="mt-1 text-xs text-gray-400 sm:text-sm">{{ stat.label }}</p>
          </div>
        </div>
      </div>

      <div class="flex flex-col items-center gap-8">
        <div
          class="group relative h-52 w-52 overflow-hidden rounded-full border-4 border-[#62BA1B] bg-gray-800 shadow-[0_0_40px_rgba(98,186,27,0.2)] sm:h-64 sm:w-64 lg:h-72 lg:w-72 animate-float"
        >
          <div
            class="absolute inset-0 z-10 bg-gradient-to-br from-[#62BA1B]/25 to-transparent opacity-0 transition-opacity duration-300 group-hover:opacity-100"
          ></div>
          <img
            class="h-full w-full object-cover transition-transform duration-700 group-hover:scale-110"
            src="/images/profile.jpg"
            alt="Hazem Hamdy - Frontend Developer"
          />
        </div>

        <div class="w-full space-y-4">
          <h3 class="text-center text-sm font-medium tracking-wider text-[#62BA1B]">
            Technologies I Work With
          </h3>
          <div class="flex flex-wrap items-center justify-center gap-3">
            <span
              v-for="(tech, index) in technologies"
              :key="tech"
              class="tech-tag"
              :style="{ animationDelay: `${index * 0.1}s` }"
            >
              {{ tech }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const stats = [
  { value: '3+', label: 'Years Exp' },
  { value: '3', label: 'Projects' },
  { value: '5', label: 'Core Stack' },
]

const technologies = ['Vue.js', 'Nuxt.js', 'React', 'TypeScript', 'Tailwind CSS']
</script>

<style scoped>
.name-gradient {
  font-family: "Raleway", sans-serif;
  background: linear-gradient(45deg, #ffffff, #62ba1b);
  background-size: 200% 200%;
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-shift 8s ease infinite;
}

.tech-tag {
  @apply rounded-xl border border-[#62BA1B] px-4 py-2 text-sm text-[#9C9C9C] transition-all duration-300 hover:bg-[#62BA1B] hover:text-white;
  animation: fade-in-up 0.5s ease-out forwards;
  opacity: 0;
  transform: translateY(20px);
}

@keyframes gradient-shift {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes fade-in-up {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes blob {
  0% {
    transform: translate(0px, 0px) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
  100% {
    transform: translate(0px, 0px) scale(1);
  }
}

@keyframes float {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-16px);
  }
  100% {
    transform: translateY(0px);
  }
}

.animate-blob {
  animation: blob 7s infinite;
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animation-delay-2000 {
  animation-delay: 2000ms;
}

.animation-delay-4000 {
  animation-delay: 4000ms;
}
</style>
