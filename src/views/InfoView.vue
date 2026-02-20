<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="my-8 self-start text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-blue-400 hover:underline"
    >
      ← Back to Links
    </RouterLink>
    <div
      class="w-full max-w-lg rounded-2xl border border-gray-700 bg-gray-800 p-6 shadow-xl shadow-gray-900/50 sm:p-8"
    >
      <div class="mb-6 flex flex-col items-center text-center sm:flex-row sm:text-left">
        <div
          class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-blue-400 sm:mr-6 sm:mb-0"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="font-display mb-1 text-2xl font-bold text-white">{{ bio.name }}</h1>
          <p class="text-sm text-gray-400">{{ bio.location }}</p>
        </div>
      </div>
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">About</h2>
        <p class="leading-relaxed text-gray-300">{{ bio.about }}</p>
      </div>
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">Skills</h2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full bg-blue-900/50 px-3 py-1 text-sm text-blue-300"
          >
            {{ skill }}
          </span>
        </div>
      </div>
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Get in Touch</h2>
        <a
          :href="'mailto:' + bio.email"
          class="group inline-flex items-center gap-2 rounded-xl bg-blue-500 px-6 py-3 font-medium text-white shadow-lg shadow-blue-500/30 transition-all duration-200 hover:scale-105 hover:bg-blue-600 hover:shadow-xl hover:shadow-blue-500/40 active:scale-95"
        >
          Send Email
        </a>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
const bio = ref({
  name: 'Marc B. Geller',
  avatar: 'IMG_WXYZ.png',
  about:
    'I am a physician assistant and recovering newspaper journalist now pursuing a Bachelor of Applied Technology in Computer and Information Technologies at South Texas College in McAllen, Texas.',
  skills: [
    'Vue.js',
    'Tailwind CSS',
    'JavaScript',
    'HTML/CSS',
    'Git/GitHub',
    'Cloudflare Pages',
    'Technical Writing',
  ],
  email: 'mgeller@stu.southtexascollege.edu',
  location: 'McAllen, Texas',
})
</script>
