<template>
  <a
    href="#"
    target="_blank"
    rel="noopener noreferrer"
    class="group relative flex w-full items-center gap-4 rounded-xl border border-gray-700 bg-gray-800 p-4 shadow-md transition-all duration-300 hover:scale-[1.02] hover:border-green-600 hover:bg-gray-900/60 hover:shadow-xl hover:shadow-green-500/20 active:scale-95"
  >
    <!-- Icon Container -->
    <div
      class="flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-lg bg-gray-700 transition-all duration-300 group-hover:scale-110 group-hover:bg-green-600 group-hover:shadow-xl group-hover:shadow-green-500/20"
    >
      <svg
        viewBox="0 0 24 24"
        fill="none"
        class="h-6 w-6 stroke-green-400 transition-transform duration-300 group-hover:rotate-6 group-hover:text-white"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
      >
        <path d="M12 2L2 7l10 5 10-5-10-5z" />
        <path d="M2 17l10 5 10-5" />
        <path d="M2 12l10 5 10-5" />
      </svg>
    </div>

    <!-- Text Content -->
    <div class="flex-shrink overflow-hidden">
      <h3 class="font-display truncate font-semibold text-white">Link Title</h3>
      <p class="truncate text-sm text-gray-400">This is just simple descriptive text.</p>
    </div>

    <!-- Glow Effect Overlay -->
    <div
      class="pointer-events-none absolute inset-0 rounded-xl bg-gradient-to-r from-green-500/0 via-green-400/10 to-green-500/0 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
    ></div>
  </a>
</template>

<script setup></script>
