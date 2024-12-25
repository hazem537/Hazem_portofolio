<template>
  <section
    id="Hero"
    class="bg-[#080808]   pt-16 transition-all duration-300 lg:pt-0 grid grid-cols-1 lg:grid-cols-2 lg:grid-rows-[auto_200px] place-items-center"
  >
    <div class="p-4 flex flex-col justfy-center order-1  transition-all duration-300 lg:order-0  items-center lg:items-start gap-10">
      <h2 class=" font-bold Name">Hazem Hamdy</h2>
      <p>hi iam frontEnd developer in nuxt</p>
      <a
      href="/cv.pdf" 
      target="_blank"
        class="px-8 py-4 flex justify-center items-center  cursor-pointer text-white font-bold bg-[#3F8E00] border border-[#62BA1B] w-[70%] relative rounded-md"
      >
        <div class="absolute inset-0 bg-[#3F8E00] z-0 blur-xl opacity-30"></div>
        <p class="z-[10] text-white text-[.8rem] font-bold relative">See My CV ></p>
      </a>
    </div>

    <div
      class=" w-[150px] h-[150px] lg:w-[200px] lg:h-[200px] rounded-full order-0 lg:order-1  flex justify-center items-center overflow-clip bg-gray-500"
    >
      <img
        class="w-full h-full rounded-full"
        src="https://media.licdn.com/dms/image/v2/D4D03AQH0pJKNXks4QA/profile-displayphoto-shrink_200_200/profile-displayphoto-shrink_200_200/0/1724169917630?e=1739404800&v=beta&t=Sj3PVbCKULEH1JbN_ACvji973qKH3BoRpAXuQ3bTJOo"
      />
    </div>
    <div class="col-span-1 lg:col-span-2 p-5 w-full h-full flex flex-col gap-5 order-3 transition-all duration-300">
      <h3>Work with</h3>
      <div class="flex justify-around items-center">
        <p class=" py-1 px-2 md:py-4 md:px-8 border rounded-xl transition-all duration-300">Qydha</p>
        <p class=" py-1 px-2 md:py-4 md:px-8 border rounded-xl transition-all duration-300">Zat</p>
        <p class=" py-1 px-2 md:py-4 md:px-8 border rounded-xl transition-all duration-300">brouj</p>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup></script>

<style scoped>
.Name {
  font-family: "Raleway", sans-serif;
  @apply text-3xl lg:text-6xl text-[#FFFFFF];
}
</style>
