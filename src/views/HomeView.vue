<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:px-6">
    <!-- Profile Header -->
    <div class="mb-8 flex flex-col items-center text-center">
      <!-- Avatar Container -->
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-blue-400 shadow-2xl shadow-blue-500/50 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>

      <!-- Name -->
      <h1 class="font-display mb-2 text-2xl font-bold text-white sm:text-3xl">
        {{ profile.name }}
      </h1>

      <!-- Slogan -->
      <p class="max-w-md text-sm text-gray-400 sm:text-base">
        {{ profile.slogan }}
      </p>
    </div>

    <!-- Link List -->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!-- Navigation to Info Page -->
    <router-link
      to="/info"
      class="mt-8 text-sm text-gray-400 underline decoration-transparent underline-offset-4 transition-colors duration-200 hover:text-blue-400 hover:decoration-blue-400"
    >
      About me →
    </router-link>
  </main>
</template>

<script setup>
import { ref } from 'vue' // add ref to the import
import LinkCard from '../components/LinkCard.vue'

const profile = ref({
  // wrap in ref()
  name: 'Marc B. Geller',
  slogan:
    'Computer & Information Technology student | Physician Assistant | recovering Newspaper Journalist',
  avatar: 'IMG_WXYZ.png',

  // ✨ Add this links array
  links: [
    {
      id: 1,
      title: 'GitHub',
      url: 'https://github.com/logonaut',
      icon: 'code',
      description: 'Check out my projects on GitHub',
    },
    {
      id: 2,
      title: 'LinkedIn',
      url: 'https://www.linkedin.com/in/marcbgeller/',
      icon: 'briefcase',
      description: 'Connect with me professionally',
    },
    {
      id: 3,
      title: 'Expense Splitter',
      url: 'https://expense-splitter-vue.paymate-vue.workers.dev/',
      icon: 'calculator',
      description: 'Vue expense tracking app',
    },
  ],
})
</script>
