<template>
  <footer class="bg-gradient-to-t from-[#1B1B1B] to-[#080808] py-12 relative overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute bottom-0 left-1/4 w-72 h-72 bg-[#62BA1B] rounded-full mix-blend-multiply filter blur-xl opacity-10 animate-blob"></div>
      <div class="absolute bottom-0 right-1/4 w-72 h-72 bg-[#3F8E00] rounded-full mix-blend-multiply filter blur-xl opacity-10 animate-blob animation-delay-2000"></div>
    </div>

    <div class="max-w-6xl mx-auto px-4 md:px-8">
      <div class="flex flex-col md:flex-row justify-between items-center gap-8">
        <!-- Contact Section -->
        <div class="flex flex-col md:flex-row gap-6 w-full md:w-auto">
          <a
            href="tel:+0201061961692"
            class="contact-button group"
          >
            <div class="contact-icon">
              <img src="~ assets/images/phone.png" alt="Phone" class="w-5 h-5" />
            </div>
            <div class="contact-content">
              <span class="contact-label">Call me</span>
              <span class="contact-value">+20 106 196 1692</span>
            </div>
          </a>

          <a
            href="mailto:hazemhamdy752@gmail.com"
            class="contact-button group"
          >
            <div class="contact-icon">
              <img src="~ assets/images/email.png" alt="Email" class="w-5 h-5" />
            </div>
            <div class="contact-content">
              <span class="contact-label">Email me</span>
              <span class="contact-value">hazemhamdy752@gmail.com</span>
            </div>
          </a>
        </div>

        <!-- Social Links -->
        <div class="flex gap-4">
          <a
            href="https://www.linkedin.com/in/hazem-hamdy-238533324/"
            target="_blank"
            class="social-link"
          >
            <img src="~ assets/images/whitelinkedin.png" alt="LinkedIn" class="w-6 h-6" />
          </a>
          <a
            href="https://github.com/hazem537"
            target="_blank"
            class="social-link"
          >
            <img src="~ assets/images/whitegithub.png" alt="GitHub" class="w-6 h-6" />
          </a>
        </div>
      </div>

      <!-- Copyright -->
      <div class="mt-8 pt-8 border-t border-[#62BA1B]/20 text-center">
        <p class="text-gray-400 text-sm">
          © {{ new Date().getFullYear() }} Hazem Hamdy. All rights reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<script lang="ts" setup>
// Add any necessary logic here
</script>

<style scoped>
.contact-button {
  @apply flex items-center gap-4 px-6 py-3 bg-[#1B1B1B]/50 backdrop-blur-sm border border-[#62BA1B]/20 rounded-xl transition-all duration-300 hover:border-[#62BA1B] hover:bg-[#1B1B1B]/80 hover:shadow-lg hover:shadow-[#62BA1B]/10;
}

.contact-icon {
  @apply w-10 h-10 flex items-center justify-center bg-[#62BA1B]/10 rounded-lg transition-transform duration-300;
}

.contact-button:hover .contact-icon {
  @apply transform scale-110 bg-[#62BA1B]/20;
}

.contact-content {
  @apply flex flex-col;
}

.contact-label {
  @apply text-sm text-gray-400;
}

.contact-value {
  @apply text-white font-medium;
}

.social-link {
  @apply w-10 h-10 flex items-center justify-center bg-[#1B1B1B]/50 backdrop-blur-sm border border-[#62BA1B]/20 rounded-lg transition-all duration-300 hover:border-[#62BA1B] hover:bg-[#1B1B1B]/80 hover:shadow-lg hover:shadow-[#62BA1B]/10;
}

.social-link:hover {
  @apply transform scale-110;
}

@keyframes blob {
  0% { transform: translate(0px, 0px) scale(1); }
  33% { transform: translate(30px, -50px) scale(1.1); }
  66% { transform: translate(-20px, 20px) scale(0.9); }
  100% { transform: translate(0px, 0px) scale(1); }
}

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2000ms;
}
</style>
