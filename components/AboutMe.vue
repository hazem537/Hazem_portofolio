<template>
  <section
    id="AboutMe"
    class="h-full bg-[#080808] w-full pt-16 md:pt-10 flex px-4 md:px-16 gap-3 flex-col justify-center items-center "
  >
    <h2 class="text-4xl   title">About Me</h2>
    <p class="md:text-sm text-xs text-center">
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
    <div class="border-t-2 h-1 w-full"></div>
    <section
      id="skills"
      class="flex flex-wrap gap-2 justify-center duration-300 transation-all"
    >
      <h2 class="Title w-full text-center text-4xl mb-4 md:text-6xl">Skills</h2>
      <div class="skill_tile bg-orange-500/30 border border-orange-500">
        <img src="~assets/images/html5.png" class="h-[32px]" />
        <p class="font-bold  ">HTML 5</p>
      </div>
      <div class="skill_tile bg-blue-500/30 border border-blue-500">
        <img src="~assets/images/css3.png" class="h-[32px]" />
        <p class="font-bold  ">CSS 3</p>
      </div>
      <div class="skill_tile bg-yellow-500/30 border border-yellow-500">
        <img src="~assets/images/js.png" class="h-[32px]" />
        <p class="font-bold  ">JavaScript</p>
      </div>
      <div class="skill_tile bg-blue-500/30 border border-blue-500">
        <img src="~assets/images/ts.png" class="h-[32px]" />
        <p class="font-bold  ">TypeScript</p>
      </div>

      <div class="skill_tile bg-blue-500/30 border border-blue-500">
        <img src="~assets/images/tailwind.png" class="h-[32px]" />
        <p class="font-bold  ">Tailwind css</p>
      </div>
      <div class="skill_tile bg-violet-500/30 border border-violet-500">
        <img src="~assets/images/bootstrap.svg" class="h-[32px]" />
        <p class="font-bold  ">Bootstrap</p>
      </div>
      <div class="skill_tile bg-red-500/30 border border-red-500">
        <img src="~assets/images/angular.png" class="h-[32px]" />
        <p class="font-bold  ">Angular</p>
      </div>
      <div class="skill_tile bg-green-500/30 border border-green-500">
        <img src="~assets/images/vue.png" class="h-[32px]" />
        <p class="font-bold  ">VueJS</p>
      </div>
      <div class="skill_tile bg-green-500/30 border border-green-500">
        <img src="~assets/images/nuxt.svg" class="h-[32px]" />
        <p class="font-bold  ">NuxtJS</p>
      </div>
      <div class="skill_tile bg-yellow-500/30 border border-yellow-500">
        <img src="~assets/images/pinia.png" class="h-[32px]" />
        <p class="font-bold  ">pinia</p>
      </div>
      <div class="skill_tile bg-green-500/30 border border-green-500">
        <img src="~assets/images/gsap.svg" class="h-[32px]" />
        <p class="font-bold  ">GSAP</p>
      </div>
      <div class="skill_tile bg-yellow-500/30 border border-yellow-500">
        <img src="~assets/images/vitest.svg" class="h-[32px]" />
        <p class="font-bold  ">Vitest</p>
      </div>
      <div class="skill_tile bg-orange-500/30 border border-orange-500">
        <img src="~assets/images/git.png" class="h-[32px]" />
        <p class="font-bold  ">Git</p>
      </div>
      <div class="skill_tile bg-white/30 border border-white">
        <img src="~assets/images/github.png" class="h-[32px]" />
        <p class="font-bold  ">GitHub</p>
      </div>
    </section>
  </section>
</template>

<script lang="ts" setup></script>

<style scooped>
.title {
  font-family: "Raleway", sans-serif;
  @apply   font-bold;
}
.skill_tile {
  @apply duration-300    text-xs px-4 py-1 rounded-xl flex gap-5 justify-between items-center;
}
.skill_tile img {
  @apply h-[20px] md:h-[22px];
}
</style>
