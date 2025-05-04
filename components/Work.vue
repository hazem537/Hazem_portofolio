<template>
  <section
    id="Work"
    class="w-full pt-[100px] md:pt-5 min-h-screen grid grid-cols-1 gap-[100px] p-5 md:p-16 md:grid-rows-[150px_auto] place-items-center bg-gradient-to-b from-[#080808] to-[#1B1B1B]"
  >
    <div class="self-end flex flex-col items-center animate-fade-in">
      <h1 class="text-5xl Title text-white mb-4">My Work</h1>
      <p class="text-sm text-gray-400 max-w-md text-center">Crafting modern web experiences with Nuxt.js and Vue.js, focusing on performance and user engagement</p>
    </div>

    <article class="work-card group">
      <div class="work-content">
        <div class="tech-badge">Nuxtjs</div>
        <h1 class="Title text-3xl text-white mb-4">Qydha</h1>
        <p class="text-gray-300 text-sm leading-relaxed">
          Welcome to Qydha — the ultimate solution for managing and calculating
          scores for the popular Baloot game. Our app is tailored for Baloot
          enthusiasts, providing a seamless and accurate way to track scores,
          enhance gameplay, and bring players closer together.
        </p>
        <a href="https://qydha.com/" class="mt-auto" target="_blank">
          <button class="work-button group">
            <span>View Website</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M5 12H19M19 12L12 5M19 12L12 19" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </a>
      </div>
      <div class="work-image-wrapper">
        <img
          class="work-image"
          src="~/assets/images/qydha.jpg"
          alt="Qydha Project Screenshot"
        />
      </div>
    </article>

    <article class="work-card group reverse">
      <div class="work-content">
        <div class="tech-badge">Nuxtjs</div>
        <h1 class="Title text-3xl text-white mb-4">Zat</h1>
        <p class="text-gray-300 text-sm leading-relaxed">
          Take your Baloot tournaments to the next level with Zat Streamer — the
          ultimate tool for managing and displaying real-time gameplay details.
          Designed for seamless integration with Qydha, Zat Streamer transforms
          the way you experience and broadcast your games.
        </p>
        <a href="https://www.youtube.com/@ZAT_PLUS/streams" target="_blank" class="mt-auto">
          <button class="work-button group">
            <span>View Videos</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M5 12H19M19 12L12 5M19 12L12 19" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </a>
      </div>
      <div class="work-image-wrapper">
        <img
          class="work-image"
          src="~/assets/images/zat.jpg"
          alt="Zat Project Screenshot"
        />
      </div>
    </article>

    <article class="work-card group">
      <div class="work-content">
        <div class="tech-badge">Nuxtjs</div>
        <h1 class="Title text-3xl text-white mb-4">Brouj</h1>
        <p class="text-gray-300 text-sm leading-relaxed">
          Welcome to Brouj – Your Trusted Partner for Unforgettable Journeys in
          Makkah and Madinah. At Brouj, we specialize in creating enriching
          tourism experiences in the holy cities of Makkah and Madinah. Our
          mission is to provide visitors with seamless travel services, ensuring
          their spiritual journey is both comfortable and memorable.
        </p>
        <a href="https://borruj.com/" target="_blank" class="mt-auto">
          <button class="work-button group">
            <span>View Website</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M5 12H19M19 12L12 5M19 12L12 19" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </a>
      </div>
      <div class="work-image-wrapper">
        <img
          class="work-image"
          src="~/assets/images/brouj.jpg"
          alt="Brouj Project Screenshot"
        />
      </div>
    </article>
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

  document.querySelectorAll('.work-card').forEach((card) => {
    observer.observe(card)
  })
})
</script>

<style>
.Title {
  font-family: "Raleway", sans-serif;
  @apply font-bold;
}

.work-card {
  @apply flex flex-col-reverse md:flex-row justify-between items-center gap-8 p-6 rounded-2xl bg-[#1B1B1B]/50 backdrop-blur-sm border border-[#62BA1B]/20 transition-all duration-500 opacity-0 transform translate-y-10;
  max-width: 1200px;
  width: 100%;
}

.work-card.reverse {
  @apply md:flex-row-reverse;
}

.work-card.animate-in {
  @apply opacity-100 translate-y-0;
}

.work-content {
  @apply flex flex-col gap-4 p-4 flex-1;
}

.work-image-wrapper {
  @apply relative overflow-hidden rounded-xl flex-1;
  aspect-ratio: 16/9;
}

.work-image {
  @apply w-full h-full object-cover transition-all duration-500;
  filter: grayscale(50%);
}

.work-card:hover .work-image {
  filter: grayscale(0%);
  transform: scale(1.05);
}

.tech-badge {
  @apply text-[#62BA1B] w-fit bg-[#62BA1B]/10 border border-[#62BA1B] text-sm rounded-xl text-center px-4 py-2 transition-all duration-300;
}

.work-card:hover .tech-badge {
  @apply bg-[#62BA1B]/20;
}

.work-button {
  @apply px-6 py-3 bg-[#62BA1B] text-white rounded-xl flex items-center gap-2 transition-all duration-300 hover:bg-[#3F8E00] hover:shadow-lg hover:shadow-[#62BA1B]/20;
}

.work-button span {
  @apply text-white font-medium;
}

.arrow-icon {
  @apply w-5 h-5 transition-transform duration-300 text-white;
}

.work-button:hover .arrow-icon {
  @apply transform translate-x-1;
}

@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 0.8s ease-out forwards;
}
</style>
