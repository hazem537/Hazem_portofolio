<template>
  <section
    id="AboutMe"
    class="min-h-screen bg-gradient-to-b from-[#080808] to-[#1B1B1B] w-full pt-32 md:pt-40 flex px-4 md:px-16 gap-8 flex-col justify-center items-center relative overflow-hidden scroll-mt-20"
  >
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute top-20 right-20 w-72 h-72 bg-[#62BA1B] rounded-full mix-blend-multiply filter blur-xl opacity-10 animate-blob"></div>
      <div class="absolute bottom-40 left-20 w-72 h-72 bg-[#3F8E00] rounded-full mix-blend-multiply filter blur-xl opacity-10 animate-blob animation-delay-2000"></div>
    </div>

    <div class="max-w-4xl w-full space-y-8 animate-fade-in">
      <h2 class="text-4xl md:text-5xl title text-white text-center">About Me</h2>
      <p class="md:text-base text-sm text-gray-300 text-center leading-relaxed">
        I am a passionate Front-End Developer with solid experience in building
        user-friendly web applications. I have a strong foundation in Angular,
        Vue.js, and Nuxt.js, with 6 months of hands-on experience in Angular and
        over a year of professional experience working with Vue.js and Nuxt.js.
        Throughout my career, I have successfully worked on various projects using
        Nuxt.js, focusing on creating efficient, scalable, and visually appealing
        web solutions. My goal is to continuously enhance my skills and contribute
        to building modern and innovative applications. I enjoy solving
        challenges, learning new technologies, and collaborating with teams to
        deliver high-quality software that meets user needs.
      </p>
    </div>

    <div class="w-full max-w-4xl border-t border-[#62BA1B]/20 my-8"></div>

    <section
      id="skills"
      class="w-full max-w-4xl space-y-8 animate-fade-in animation-delay-200"
    >
      <h2 class="Title text-center text-4xl md:text-5xl text-white mb-8">Skills</h2>
      <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
        <div class="skill-card" data-skill="HTML5">
          <div class="skill-icon">
            <img src="~assets/images/html5.png" alt="HTML5" />
          </div>
          <p class="skill-name">HTML 5</p>
        </div>

        <div class="skill-card" data-skill="CSS3">
          <div class="skill-icon">
            <img src="~assets/images/css3.png" alt="CSS3" />
          </div>
          <p class="skill-name">CSS 3</p>
        </div>

        <div class="skill-card" data-skill="JavaScript">
          <div class="skill-icon">
            <img src="~assets/images/js.png" alt="JavaScript" />
          </div>
          <p class="skill-name">JavaScript</p>
        </div>

        <div class="skill-card" data-skill="TypeScript">
          <div class="skill-icon">
            <img src="~assets/images/ts.png" alt="TypeScript" />
          </div>
          <p class="skill-name">TypeScript</p>
        </div>

        <div class="skill-card" data-skill="Tailwind">
          <div class="skill-icon">
            <img src="~assets/images/tailwind.png" alt="Tailwind CSS" />
          </div>
          <p class="skill-name">Tailwind CSS</p>
        </div>

        <div class="skill-card" data-skill="Bootstrap">
          <div class="skill-icon">
            <img src="~assets/images/bootstrap.svg" alt="Bootstrap" />
          </div>
          <p class="skill-name">Bootstrap</p>
        </div>

        <div class="skill-card" data-skill="Angular">
          <div class="skill-icon">
            <img src="~assets/images/angular.png" alt="Angular" />
          </div>
          <p class="skill-name">Angular</p>
        </div>

        <div class="skill-card" data-skill="VueJS">
          <div class="skill-icon">
            <img src="~assets/images/vue.png" alt="Vue.js" />
          </div>
          <p class="skill-name">Vue.js</p>
        </div>

        <div class="skill-card" data-skill="NuxtJS">
          <div class="skill-icon">
            <img src="~assets/images/nuxt.svg" alt="Nuxt.js" />
          </div>
          <p class="skill-name">Nuxt.js</p>
        </div>

        <div class="skill-card" data-skill="Pinia">
          <div class="skill-icon">
            <img src="~assets/images/pinia.png" alt="Pinia" />
          </div>
          <p class="skill-name">Pinia</p>
        </div>

        <div class="skill-card" data-skill="GSAP">
          <div class="skill-icon">
            <img src="~assets/images/gsap.svg" alt="GSAP" />
          </div>
          <p class="skill-name">GSAP</p>
        </div>

        <div class="skill-card" data-skill="Vitest">
          <div class="skill-icon">
            <img src="~assets/images/vitest.svg" alt="Vitest" />
          </div>
          <p class="skill-name">Vitest</p>
        </div>

        <div class="skill-card" data-skill="Git">
          <div class="skill-icon">
            <img src="~assets/images/git.png" alt="Git" />
          </div>
          <p class="skill-name">Git</p>
        </div>

        <div class="skill-card" data-skill="GitHub">
          <div class="skill-icon">
            <img src="~assets/images/github.png" alt="GitHub" />
          </div>
          <p class="skill-name">GitHub</p>
        </div>
      </div>
    </section>
  </section>
</template>

<script lang="ts" setup>
// Add intersection observer for scroll animations
onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-in')
      }
    })
  }, {
    threshold: 0.1
  })

  document.querySelectorAll('.skill-card').forEach((card) => {
    observer.observe(card)
  })
})
</script>

<style scoped>
.title {
  font-family: "Raleway", sans-serif;
  @apply font-bold;
}

.skill-card {
  @apply bg-[#1B1B1B]/50 backdrop-blur-sm border border-[#62BA1B]/20 rounded-xl p-4 flex flex-col items-center gap-3 transition-all duration-300 hover:border-[#62BA1B] hover:bg-[#1B1B1B]/80 hover:shadow-lg hover:shadow-[#62BA1B]/10;
  opacity: 0;
  transform: translateY(20px);
}

.skill-card.animate-in {
  animation: fade-in-up 0.5s ease-out forwards;
}

.skill-icon {
  @apply w-12 h-12 flex items-center justify-center bg-white/5 rounded-lg p-2 transition-transform duration-300;
}

.skill-card:hover .skill-icon {
  @apply transform scale-110;
}

.skill-name {
  @apply text-white font-medium text-sm;
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
  0% { transform: translate(0px, 0px) scale(1); }
  33% { transform: translate(30px, -50px) scale(1.1); }
  66% { transform: translate(-20px, 20px) scale(0.9); }
  100% { transform: translate(0px, 0px) scale(1); }
}

.animate-fade-in {
  animation: fade-in 0.8s ease-out forwards;
}

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-200 {
  animation-delay: 200ms;
}

.animation-delay-2000 {
  animation-delay: 2000ms;
}

@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}
</style>
