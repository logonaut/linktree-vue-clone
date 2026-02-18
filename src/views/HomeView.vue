<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:px-6">
    <!-- Profile Header -->
    <div class="mb-8 flex flex-col items-center text-center">
      <!-- Avatar Container -->
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-green-400 shadow-2xl shadow-green-500/50 sm:h-32 sm:w-32"
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
      <!-- Repeat LinkCard component 3 times -->
      <LinkCard
        v-for="x in [1, 2, 3]"
        :key="x"
      />
    </div>

    <!-- Navigation to Info Page -->
    <router-link
      to="/info"
      class="mt-8 text-sm text-gray-400 underline decoration-transparent underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:decoration-green-400"
    >
      About me →
    </router-link>
  </main>
</template>

<script setup>
import LinkCard from '../components/LinkCard.vue'

const profile = {
  name: 'Marc B. Geller',
  slogan:
    'Computer & Information Technology student | Physician Assistant | recovering Newspaper Journalist',
  avatar: 'IMG_WXYZ.png',
}
</script>
