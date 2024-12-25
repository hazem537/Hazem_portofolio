<template>
  <section
    id="Work"
    class="w-full pt-[100px] md:pt-5 min-h-screen grid grid-cols-1 gap-[100px] p-5 md:p-16 md:grid-rows-[150px_auto] place-items-center"
  >
    <div class="self-end flex flex-col items-center">
      <h1 class="text-5xl Title">My Work</h1>
      <p class="text-sm">this work in front end field using nuxtjs and vuejs</p>
    </div>

    <article class="flex flex-col-reverse gap-5 md:flex-row justify-between group">
      <div class="flex flex-col gap-4 p-4">
        <p
          class="text-green-500 w-[100px] bg-green-500/30 border text-sm  border-green-500 rounded-xl text-center px-3 py-1"
        >
          Nuxtjs
        </p>
        <h1 class="Title text-center  md:text-left text-3xl">Qydha</h1>
        <p class="text-sm text-center truncate text-wrap">
          Welcome to Qydha — the ultimate solution for managing and calculating
          scores for the popular Baloot game. Our app is tailored for Baloot
          enthusiasts, providing a seamless and accurate way to track scores,
          enhance gameplay, and bring players closer together.
        </p>
        <a href="https://qydha.com/" class="mt-auto" target="_blank">
          <button
            class="px-4 py-2 w-[200px] bg-green-500 text-white rounded-xl"
          >
            view Website >
          </button>
        </a>
      </div>
      <img
        class="rounded-xl w-[100%] md:w-[50%]  grayscale-[50%] group-hover:grayscale-0 transition-all duration-300"
        src="../assets/images/qydha.jpg"
      />
    </article>

    <article
      class="flex flex-col-reverse gap-5 md:flex-row-reverse justify-between group"
    >
      <div class="flex flex-col gap-4 p-4">
        <p
          class="text-green-500 w-[100px] bg-green-500/30 border text-sm border-green-500 rounded-xl text-center px-3 py-1"
        >
          Nuxtjs
        </p>
        <h1 class="Title  text-center  md:text-left text-3xl">Zat</h1>
        <p class="text-sm text-center truncate text-wrap">
          Take your Baloot tournaments to the next level with Zat Streamer — the
          ultimate tool for managing and displaying real-time gameplay details.
          Designed for seamless integration with Qydha, Zat Streamer transforms
          the way you experience and broadcast your games.
        </p>
        <a
          href="https://www.youtube.com/@ZAT_PLUS/streams"
          target="_blank"
          class="mt-auto"
        >
          <button
            class="px-4 py-2 w-[200px] bg-green-500 text-white rounded-xl"
          >
            view videos >
          </button>
        </a>
      </div>
      <img
        class="rounded-xl w-[100%]  md:h-auto md:w-[50%] grayscale-[50%] group-hover:grayscale-0 transition-all duration-300"
        src="../assets/images/zat.jpg"
      />
    </article>

    <article class="flex flex-col-reverse gap-5 md:flex-row justify-between group">
      <div class="flex flex-col gap-4 p-4">
        <p
          class="text-green-500 w-[100px] bg-green-500/30 border text-sm border-green-500 rounded-xl text-center px-3 py-1"
        >
          Nuxtjs
        </p>
        <h1 class="Title  text-center  md:text-left text-3xl">Brouj</h1>
        <p class="text-sm  text-center truncate text-wrap  ">
          Welcome to Brouj – Your Trusted Partner for Unforgettable Journeys in
          Makkah and Madinah At Brouj, we specialize in creating enriching
          tourism experiences in the holy cities of Makkah and Madinah. Our
          mission is to provide visitors with seamless travel services, ensuring
          their spiritual journey is both comfortable and memorable.
        </p>
        <a href="https://borruj.com/" target="_blank" class="mt-auto">
          <button
            class="px-4 py-2 w-[200px]  bg-green-500 text-white rounded-xl"
          >
            view Website >
          </button>
        </a>
      </div>
      <img
        class="rounded-xl w-[100%] md:w-[50%]  grayscale-[50%] group-hover:grayscale-0 transition-all duration-300"
        src="../assets/images/brouj.jpg"
      />
    </article>
  </section>
</template>

<script lang="ts" setup></script>

<style>
.Title {
  font-family: "Raleway", sans-serif;
  @apply text-[#080808]  font-bold;
}
</style>
