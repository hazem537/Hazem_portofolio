<template>
  <section
    id="AboutMe"
    class="relative min-h-screen overflow-hidden bg-gradient-to-b from-[#1B1B1B] to-[#080808] px-4 py-24 md:px-8 md:py-28 scroll-mt-20"
  >
    <div class="pointer-events-none absolute inset-0 overflow-hidden">
      <div
        class="absolute right-16 top-24 h-72 w-72 rounded-full bg-[#62BA1B] opacity-10 blur-3xl mix-blend-multiply animate-blob"
      ></div>
      <div
        class="absolute bottom-24 left-16 h-72 w-72 rounded-full bg-[#3F8E00] opacity-10 blur-3xl mix-blend-multiply animate-blob animation-delay-2000"
      ></div>
    </div>

    <div class="relative z-10 mx-auto max-w-5xl space-y-14">
      <div class="mx-auto max-w-3xl space-y-6 text-center">
        <h2 class="section-title text-4xl text-white md:text-5xl">About Me</h2>
        <p class="text-sm leading-relaxed text-gray-300 md:text-base">
          {{ bio }}
        </p>
      </div>

      <div class="grid grid-cols-1 gap-4 sm:grid-cols-3">
        <div
          v-for="stat in aboutStats"
          :key="stat.label"
          class="rounded-2xl border border-[#62BA1B]/20 bg-[#1B1B1B]/60 p-6 text-center backdrop-blur-sm transition-all duration-300 hover:border-[#62BA1B]/50 hover:bg-[#1B1B1B]/80"
        >
          <p class="text-3xl font-bold text-white">{{ stat.value }}</p>
          <p class="mt-2 text-sm text-gray-400">{{ stat.label }}</p>
          <p class="mt-1 text-xs text-[#62BA1B]">{{ stat.detail }}</p>
        </div>
      </div>

      <div class="border-t border-[#62BA1B]/20"></div>

      <section id="skills" class="space-y-8">
        <div class="text-center">
          <h2 class="section-title mb-3 text-4xl text-white md:text-5xl">Skills</h2>
          <p class="text-sm text-gray-400">
            A data-ready overview of the technologies I use day to day.
          </p>
        </div>

        <div class="grid grid-cols-2 gap-4 md:grid-cols-3 lg:grid-cols-4">
          <div
            v-for="(skill, index) in skills"
            :key="skill.name"
            class="skill-card"
            :class="{ 'animate-in': visibleSkills.has(index) }"
            :ref="(el) => setSkillRef(el, index)"
          >
            <div class="skill-icon">
              <img
                v-if="skill.icon"
                :src="skill.icon"
                :alt="skill.name"
                class="h-full w-full object-contain"
              />
              <span v-else class="skill-initial">{{ skill.initial }}</span>
            </div>
            <p class="skill-name">{{ skill.name }}</p>
            <p class="text-xs text-[#62BA1B]">{{ skill.category }}</p>
          </div>
        </div>
      </section>
    </div>
  </section>
</template>

<script lang="ts" setup>
import html5 from '~/assets/images/html5.png'
import css3 from '~/assets/images/css3.png'
import js from '~/assets/images/js.png'
import ts from '~/assets/images/ts.png'
import tailwind from '~/assets/images/tailwind.png'
import bootstrap from '~/assets/images/bootstrap.svg'
import react from '~/assets/images/react.webp'
import vue from '~/assets/images/vue.png'
import nuxt from '~/assets/images/nuxt.svg'
import pinia from '~/assets/images/pinia.png'
import gsap from '~/assets/images/gsap.svg'
import cursor from '~/assets/images/cursor.avif'
import git from '~/assets/images/git.png'
import github from '~/assets/images/github.png'

const bio =
  'I am a passionate Front-End Developer with solid experience in building user-friendly web applications. I have a strong foundation in Vue.js, Nuxt.js, and React, with over 3 years of professional experience shipping modern web products. Throughout my career, I have successfully worked on various projects using Nuxt.js and React, focusing on creating efficient, scalable, and visually appealing web solutions. My goal is to continuously enhance my skills and contribute to building modern and innovative applications, including AI-assisted workflows with Cursor.'

const aboutStats = [
  { value: '3+', label: 'Years Experience', detail: 'Vue, Nuxt & React' },
  { value: '3', label: 'Shipped Projects', detail: 'Qydha, Zat, Brouj' },
  { value: '15', label: 'Core Skills', detail: 'Frontend + tooling' },
]

const skills = [
  { name: 'HTML 5', category: 'Markup', icon: html5 },
  { name: 'CSS 3', category: 'Styling', icon: css3 },
  { name: 'JavaScript', category: 'Language', icon: js },
  { name: 'TypeScript', category: 'Language', icon: ts },
  { name: 'Tailwind CSS', category: 'Styling', icon: tailwind },
  { name: 'Bootstrap', category: 'Styling', icon: bootstrap },
  { name: 'React', category: 'Framework', icon: react },
  { name: 'Vue.js', category: 'Framework', icon: vue },
  { name: 'Nuxt.js', category: 'Framework', icon: nuxt },
  { name: 'Pinia', category: 'State', icon: pinia },
  { name: 'Axios', category: 'HTTP', initial: 'Ax' },
  { name: 'GSAP', category: 'Animation', icon: gsap },
  { name: 'Cursor AI', category: 'AI', icon: cursor },

  { name: 'Git', category: 'Tooling', icon: git },
  { name: 'GitHub', category: 'Tooling', icon: github },
]

const skillRefs = ref<(Element | null)[]>([])
const visibleSkills = ref(new Set<number>())

const setSkillRef = (el: Element | ComponentPublicInstance | null, index: number) => {
  if (el && '$el' in el) {
    skillRefs.value[index] = el.$el as Element
  } else {
    skillRefs.value[index] = el as Element | null
  }
}

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (!entry.isIntersecting) return
        const index = skillRefs.value.findIndex((node) => node === entry.target)
        if (index !== -1) {
          visibleSkills.value.add(index)
          visibleSkills.value = new Set(visibleSkills.value)
        }
      })
    },
    { threshold: 0.1 }
  )

  skillRefs.value.forEach((card) => {
    if (card) observer.observe(card)
  })

  onBeforeUnmount(() => observer.disconnect())
})
</script>

<style scoped>
.section-title {
  font-family: "Raleway", sans-serif;
  @apply font-bold;
}

.skill-card {
  @apply flex flex-col items-center gap-2 rounded-xl border border-[#62BA1B]/20 bg-[#1B1B1B]/50 p-4 opacity-0 backdrop-blur-sm transition-all duration-300 hover:border-[#62BA1B] hover:bg-[#1B1B1B]/80 hover:shadow-lg hover:shadow-[#62BA1B]/10;
  transform: translateY(20px);
}

.skill-card.animate-in {
  animation: fade-in-up 0.5s ease-out forwards;
}

.skill-icon {
  @apply flex h-12 w-12 items-center justify-center rounded-lg bg-white/5 p-2 transition-transform duration-300;
}

.skill-card:hover .skill-icon {
  transform: scale(1.1);
}

.skill-name {
  @apply text-sm font-medium text-white;
}

.skill-initial {
  @apply text-sm font-bold text-[#62BA1B];
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

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2000ms;
}
</style>
