<template>
  <section
    id="Hero"
    class="min-h-screen bg-[#080808] pt-16 transition-all duration-300 lg:pt-0 grid grid-cols-1 lg:grid-cols-2 lg:grid-rows-[auto_200px] place-items-center relative overflow-hidden"
  >
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute top-20 left-20 w-72 h-72 bg-[#62BA1B] rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob"></div>
      <div class="absolute top-40 right-20 w-72 h-72 bg-[#3F8E00] rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob animation-delay-2000"></div>
      <div class="absolute -bottom-8 left-20 w-72 h-72 bg-[#62BA1B] rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob animation-delay-4000"></div>
    </div>

    <div class="p-4 flex flex-col justify-center order-1 transition-all duration-300 lg:order-0 items-center lg:items-start gap-10 animate-fade-in relative z-10">
      <div class="space-y-6">
        <div class="relative">
          <span class="text-[#62BA1B] text-sm font-mono tracking-wider animate-fade-in">Hi, my name is</span>
          <h2 class="font-bold Name animate-slide-up mt-2">Hazem Hamdy</h2>
        </div>
        <div class="space-y-4">
          <h3 class="text-2xl lg:text-3xl text-[#62BA1B] animate-slide-up animation-delay-200">
            <span class="inline-block animate-typing">Frontend Developer</span>
          </h3>
          <p class="text-gray-300 max-w-lg text-lg leading-relaxed animate-slide-up animation-delay-400">
            Passionate frontend developer specializing in Nuxt.js, Vue.js, and modern web technologies. Creating beautiful and performant web experiences.
          </p>
        </div>
      </div>
      <div class="flex gap-4 animate-slide-up animation-delay-600">
        <a
          href="/cv.pdf" 
          target="_blank"
          class="group px-8 py-4 flex justify-center items-center cursor-pointer text-white font-bold bg-[#3F8E00] border border-[#62BA1B] w-auto relative rounded-md hover:bg-[#62BA1B] transition-all duration-300 hover:scale-105 hover:shadow-lg hover:shadow-[#62BA1B]/20"
        >
          <div class="absolute inset-0 bg-[#3F8E00] z-0 blur-xl opacity-30 animate-pulse"></div>
          <p class="z-[10] text-white text-[.8rem] font-bold relative group-hover:scale-105 transition-transform">Download CV</p>
        </a>
        <a
          href="#Contact"
          class="group px-8 py-4 flex justify-center items-center cursor-pointer text-white font-bold border border-[#62BA1B] w-auto relative rounded-md hover:bg-[#62BA1B] transition-all duration-300 hover:scale-105 hover:shadow-lg hover:shadow-[#62BA1B]/20"
        >
          <p class="text-[.8rem] font-bold relative group-hover:scale-105 transition-transform">Contact Me</p>
        </a>
      </div>
    </div>

    <div
      class="w-[200px] h-[200px] lg:w-[300px] lg:h-[300px] rounded-full order-0 lg:order-1 flex justify-center items-center overflow-hidden bg-gray-800 border-4 border-[#62BA1B] animate-float relative z-10 group"
    >
      <div class="absolute inset-0 bg-gradient-to-br from-[#62BA1B]/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <img
        class="w-full h-full object-cover hover:scale-110 transition-transform duration-700"
        src="/images/profile.jpg"
        alt="Hazem Hamdy - Frontend Developer"
      />
    </div>

    <div class="col-span-1 lg:col-span-2 p-5 w-full h-full flex flex-col gap-5 order-3 transition-all duration-300 animate-fade-in animation-delay-800 relative z-10">
      <h3 class="text-xl text-center text-[#62BA1B] font-mono tracking-wider">Technologies I Work With</h3>
      <div class="flex flex-wrap justify-center items-center gap-4">
        <p class="tech-tag">Vue.js</p>
        <p class="tech-tag">Nuxt.js</p>
        <p class="tech-tag">TypeScript</p>
        <p class="tech-tag">Tailwind CSS</p>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup></script>

<style scoped>
.Name {
  font-family: "Raleway", sans-serif;
  @apply text-4xl lg:text-7xl text-[#FFFFFF];
  background: linear-gradient(45deg, #FFFFFF, #62BA1B);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-shift 8s ease infinite;
  background-size: 200% 200%;
}

.tech-tag {
  @apply py-2 px-4 border border-[#62BA1B] rounded-xl transition-all duration-300 hover:bg-[#62BA1B] hover:text-white;
  animation: fade-in-up 0.5s ease-out forwards;
  opacity: 0;
  transform: translateY(20px);
}

.tech-tag:nth-child(1) { animation-delay: 0.1s; }
.tech-tag:nth-child(2) { animation-delay: 0.2s; }
.tech-tag:nth-child(3) { animation-delay: 0.3s; }
.tech-tag:nth-child(4) { animation-delay: 0.4s; }

@keyframes gradient-shift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
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

@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

.animate-fade-in {
  animation: fade-in 1s ease-out forwards;
}

.animate-slide-up {
  animation: slide-up 0.8s ease-out forwards;
  opacity: 0;
  transform: translateY(30px);
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-blob {
  animation: blob 7s infinite;
}

.animate-typing {
  overflow: hidden;
  white-space: nowrap;
  animation: typing 3.5s steps(40, end);
}

.animation-delay-200 {
  animation-delay: 200ms;
}

.animation-delay-400 {
  animation-delay: 400ms;
}

.animation-delay-600 {
  animation-delay: 600ms;
}

.animation-delay-800 {
  animation-delay: 800ms;
}

.animation-delay-2000 {
  animation-delay: 2000ms;
}

.animation-delay-4000 {
  animation-delay: 4000ms;
}

@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slide-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes float {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-20px); }
  100% { transform: translateY(0px); }
}
</style>
