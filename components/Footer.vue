<template>
  <footer
    id="Contact"
    class="relative overflow-hidden bg-gradient-to-t from-[#1B1B1B] to-[#080808] py-16 scroll-mt-20"
  >
    <div class="pointer-events-none absolute inset-0 overflow-hidden">
      <div
        class="absolute bottom-0 left-1/4 h-72 w-72 rounded-full bg-[#62BA1B] opacity-10 blur-3xl mix-blend-multiply animate-blob"
      ></div>
      <div
        class="absolute bottom-0 right-1/4 h-72 w-72 rounded-full bg-[#3F8E00] opacity-10 blur-3xl mix-blend-multiply animate-blob animation-delay-2000"
      ></div>
    </div>

    <div class="relative z-10 mx-auto max-w-6xl px-4 md:px-8">
      <div class="mb-10 text-center">
        <h2 class="section-title mb-3 text-3xl text-white md:text-4xl">Get In Touch</h2>
        <p class="text-sm text-gray-400">
          Open to frontend roles, collaborations, and interesting product work.
        </p>
      </div>

      <div class="flex flex-col items-center justify-between gap-8 md:flex-row">
        <div class="flex w-full flex-col gap-4 md:w-auto md:flex-row">
          <a href="tel:+201061961692" class="contact-button group">
            <div class="contact-icon">
              <img src="~/assets/images/phone.png" alt="" class="h-5 w-5" />
            </div>
            <div class="contact-content">
              <span class="contact-label">Call me</span>
              <span class="contact-value">+20 106 196 1692</span>
            </div>
          </a>

          <a href="mailto:hazem._hamdy@outlook.com" class="contact-button group">
            <div class="contact-icon">
              <img src="~/assets/images/email.png" alt="" class="h-5 w-5" />
            </div>
            <div class="contact-content">
              <span class="contact-label">Email me</span>
              <span class="contact-value">hazem._hamdy@outlook.com</span>
            </div>
          </a>
        </div>

        <div class="flex gap-3">
          <a
            href="https://www.linkedin.com/in/hazem-hamdy-238533324/"
            target="_blank"
            rel="noopener noreferrer"
            class="social-link"
            aria-label="LinkedIn profile"
          >
            <img
              src="~/assets/images/whitelinkedin.png"
              alt=""
              class="h-6 w-6"
            />
          </a>
          <a
            href="https://github.com/hazem537"
            target="_blank"
            rel="noopener noreferrer"
            class="social-link"
            aria-label="GitHub profile"
          >
            <img
              src="~/assets/images/whitegithub.png"
              alt=""
              class="h-6 w-6"
            />
          </a>
        </div>
      </div>

      <div class="mt-10 border-t border-[#62BA1B]/20 pt-8 text-center">
        <p class="text-sm text-gray-400">
          © {{ currentYear }} Hazem Hamdy. All rights reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<script lang="ts" setup>
const currentYear = new Date().getFullYear()
</script>

<style scoped>
.section-title {
  font-family: "Raleway", sans-serif;
  @apply font-bold;
}

.contact-button {
  @apply flex items-center gap-4 rounded-xl border border-[#62BA1B]/20 bg-[#1B1B1B]/50 px-6 py-3 backdrop-blur-sm transition-all duration-300 hover:border-[#62BA1B] hover:bg-[#1B1B1B]/80 hover:shadow-lg hover:shadow-[#62BA1B]/10;
}

.contact-icon {
  @apply flex h-10 w-10 items-center justify-center rounded-lg bg-[#62BA1B]/10 transition-transform duration-300;
}

.contact-button:hover .contact-icon {
  @apply bg-[#62BA1B]/20;
  transform: scale(1.1);
}

.contact-content {
  @apply flex flex-col;
}

.contact-label {
  @apply text-sm text-gray-400;
}

.contact-value {
  @apply font-medium text-white;
}

.social-link {
  @apply flex h-11 w-11 items-center justify-center rounded-lg border border-[#62BA1B]/20 bg-[#1B1B1B]/50 backdrop-blur-sm transition-all duration-300 hover:border-[#62BA1B] hover:bg-[#1B1B1B]/80 hover:shadow-lg hover:shadow-[#62BA1B]/10;
}

.social-link:hover {
  transform: scale(1.08);
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
