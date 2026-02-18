<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:px-6">
    <h1 class="font-display mb-6 text-3xl font-bold text-white">About Me</h1>

    <p class="mb-8 max-w-2xl text-center text-gray-400">
      Other page content will go here. This is where you can add more detailed information about
      yourself, your projects, or anything else you'd like to share.
    </p>

    <!-- Back Navigation -->
    <router-link
      to="/"
      class="text-sm text-gray-400 underline decoration-transparent underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:decoration-green-400"
    >
      ← Back to links
    </router-link>
  </main>
</template>

<script setup></script>
