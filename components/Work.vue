<template>
  <section
    id="Work"
    class="relative min-h-screen bg-gradient-to-b from-[#080808] to-[#1B1B1B] px-4 py-24 md:px-8 md:py-28"
  >
    <div class="mx-auto mb-14 max-w-3xl text-center">
      <h2 class="section-title mb-4 text-4xl text-white md:text-5xl">My Work</h2>
      <p class="mx-auto max-w-md text-sm leading-relaxed text-gray-400 md:text-base">
        Crafting modern web experiences with Nuxt.js and Vue.js, focusing on
        performance and user engagement.
      </p>
    </div>

    <div class="mx-auto flex max-w-6xl flex-col gap-10">
      <article
        v-for="(project, index) in projects"
        :key="project.title"
        class="work-card group"
        :class="{ reverse: index % 2 === 1, 'animate-in': visibleCards.has(index) }"
        :ref="(el) => setCardRef(el, index)"
      >
        <div class="work-content">
          <div class="flex flex-wrap gap-2">
            <span
              v-for="tech in project.tech"
              :key="tech"
              class="tech-badge"
            >
              {{ tech }}
            </span>
          </div>

          <h3 class="section-title text-2xl text-white md:text-3xl">
            {{ project.title }}
          </h3>

          <p class="text-sm leading-relaxed text-gray-300 md:text-base">
            {{ project.description }}
          </p>

          <a
            :href="project.href"
            class="mt-auto inline-flex"
            target="_blank"
            rel="noopener noreferrer"
          >
            <button type="button" class="work-button">
              <span>{{ project.cta }}</span>
              <svg
                class="arrow-icon"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
                aria-hidden="true"
              >
                <path
                  d="M5 12H19M19 12L12 5M19 12L12 19"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </button>
          </a>
        </div>

        <div class="work-image-wrapper">
          <img
            class="work-image"
            :src="project.image"
            :alt="`${project.title} project screenshot`"
          />
        </div>
      </article>
    </div>
  </section>
</template>

<script lang="ts" setup>
import qydhaImg from '~/assets/images/qydha.jpg'
import zatImg from '~/assets/images/zat.jpg'
import broujImg from '~/assets/images/brouj.jpg'

const projects = [
  {
    title: 'Qydha',
    description:
      'Welcome to Qydha — the ultimate solution for managing and calculating scores for the popular Baloot game. Our app is tailored for Baloot enthusiasts, providing a seamless and accurate way to track scores, enhance gameplay, and bring players closer together.',
    href: 'https://qydha.com/',
    cta: 'View Website',
    tech: ['Nuxt.js', 'Vue.js', 'TypeScript'],
    image: qydhaImg,
  },
  {
    title: 'Zat',
    description:
      'Take your Baloot tournaments to the next level with Zat Streamer — the ultimate tool for managing and displaying real-time gameplay details. Designed for seamless integration with Qydha, Zat Streamer transforms the way you experience and broadcast your games.',
    href: 'https://www.youtube.com/@ZAT_PLUS/streams',
    cta: 'View Videos',
    tech: ['Nuxt.js', 'Realtime UI'],
    image: zatImg,
  },
  {
    title: 'Brouj',
    description:
      'Welcome to Brouj – Your Trusted Partner for Unforgettable Journeys in Makkah and Madinah. At Brouj, we specialize in creating enriching tourism experiences in the holy cities of Makkah and Madinah. Our mission is to provide visitors with seamless travel services, ensuring their spiritual journey is both comfortable and memorable.',
    href: 'https://borruj.com/',
    cta: 'View Website',
    tech: ['Nuxt.js', 'Tourism'],
    image: broujImg,
  },
]

const cardRefs = ref<(Element | null)[]>([])
const visibleCards = ref(new Set<number>())

const setCardRef = (el: Element | ComponentPublicInstance | null, index: number) => {
  if (el && '$el' in el) {
    cardRefs.value[index] = el.$el as Element
  } else {
    cardRefs.value[index] = el as Element | null
  }
}

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (!entry.isIntersecting) return
        const index = cardRefs.value.findIndex((node) => node === entry.target)
        if (index !== -1) {
          visibleCards.value.add(index)
          visibleCards.value = new Set(visibleCards.value)
        }
      })
    },
    { threshold: 0.15 }
  )

  cardRefs.value.forEach((card) => {
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

.work-card {
  @apply flex w-full flex-col-reverse items-center gap-8 rounded-2xl border border-[#62BA1B]/20 bg-[#1B1B1B]/50 p-6 opacity-0 backdrop-blur-sm transition-all duration-500 md:flex-row;
  transform: translateY(24px);
}

.work-card.reverse {
  @apply md:flex-row-reverse;
}

.work-card.animate-in {
  @apply opacity-100;
  transform: translateY(0);
}

.work-card:hover {
  @apply border-[#62BA1B]/40 shadow-lg shadow-[#62BA1B]/10;
}

.work-content {
  @apply flex flex-1 flex-col gap-4 p-2 md:p-4;
}

.work-image-wrapper {
  @apply relative flex-1 overflow-hidden rounded-xl;
  aspect-ratio: 16 / 9;
}

.work-image {
  @apply h-full w-full object-cover transition-all duration-500;
  filter: grayscale(40%);
}

.work-card:hover .work-image {
  filter: grayscale(0%);
  transform: scale(1.05);
}

.tech-badge {
  @apply rounded-xl border border-[#62BA1B] bg-[#62BA1B]/10 px-3 py-1.5 text-xs text-[#62BA1B] transition-all duration-300 md:text-sm;
}

.work-card:hover .tech-badge {
  @apply bg-[#62BA1B]/20;
}

.work-button {
  @apply flex items-center gap-2 rounded-xl bg-[#62BA1B] px-6 py-3 text-white transition-all duration-300 hover:bg-[#3F8E00] hover:shadow-lg hover:shadow-[#62BA1B]/20;
}

.work-button span {
  @apply font-medium text-white;
}

.arrow-icon {
  @apply h-5 w-5 text-white transition-transform duration-300;
}

.work-button:hover .arrow-icon {
  transform: translateX(4px);
}
</style>
