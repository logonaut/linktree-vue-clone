<template>
  <a
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="group relative flex w-full items-center gap-4 rounded-xl border border-gray-700 bg-gray-800 p-4 shadow-md shadow-gray-900/50 transition-all duration-300 hover:scale-[1.02] hover:border-blue-600 hover:shadow-xl hover:shadow-blue-500/20 active:scale-95"
  >
    <!-- Icon Container -->
    <div
      class="flex h-12 w-12 shrink-0 items-center justify-center rounded-lg bg-gray-700 text-blue-400 transition-all duration-300 group-hover:scale-110 group-hover:bg-blue-500 group-hover:text-white group-hover:shadow-xl group-hover:shadow-blue-500/20"
    >
      <svg
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        class="h-6 w-6 transition-transform duration-300 group-hover:rotate-6"
        v-html="icons[icon] || icons.flag"
      ></svg>
    </div>

    <!-- Text Content -->
    <div class="min-w-0 flex-1">
      <h3 class="font-display truncate font-semibold text-white">{{ title }}</h3>
      <p class="truncate text-sm text-gray-400">{{ description }}</p>
    </div>

    <!-- Hover Glow Effect -->
    <div
      class="pointer-events-none absolute inset-0 rounded-xl bg-gradient-to-r from-blue-500/0 via-blue-500/10 to-blue-500/0 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
    />
  </a>
</template>

<script setup>
// defineProps is a compiler macro — no import needed
defineProps({
  title: {
    type: String,
    required: true,
  },
  url: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    default: '', // renders nothing if parent doesn't pass it
  },
  icon: {
    type: String,
    default: 'flag', // falls back to the flag icon
  },
})

const icons = {
  // Default fallback
  flag: `<path
    stroke-linecap="round"
    stroke-linejoin="round"
    stroke-width="2"
    d="M6 12v9a1 1 0 0 1-2 0V4c0-1.1.9-2 2-2h6c1.1 0 1.999.9 1.999 2H18a2 2 0 0 1 2 2v6
       a2 2 0 0 1-2 2h-5a2 2 0 0 1-1.997-2zm0-8v6h7v2h5.002V6H12V4z"
  />`,

  // Code brackets — for GitHub / dev links  (from instructor exemplar)
  code: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5"></path>',

  // Briefcase — for LinkedIn / professional links  (from instructor exemplar)
  briefcase:
    '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 0 0 .75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 0 0-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0 1 12 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 0 1-.673-.38m0 0A2.18 2.18 0 0 1 3 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 0 1 3.413-.387m7.5 0V5.25A2.25 2.25 0 0 0 13.5 3h-3a2.25 2.25 0 0 0-2.25 2.25v.894m7.5 0a48.667 48.667 0 0 0-7.5 0M12 12.75h.008v.008H12v-.008Z"></path>',

  // Calculator — for Expense Splitter card
  calculator:
    '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.75 15.75V18m-7.5-6.75h.008v.008H8.25v-.008zm0 2.25h.008v.008H8.25v-.008zm0 2.25h.008v.008H8.25V15zm2.498-4.5h.008v.008h-.008v-.008zm0 2.25h.008v.008h-.008v-.008zm0 2.25h.008v.008h-.008V15zm2.247-4.5h.008v.008h-.008v-.008zm0 2.25h.008v.008h-.008v-.008zm0 2.25h.008v.008h-.008V15zm2.498-6.75h.008v.008h-.008v-.008zm0 2.25h.008v.008h-.008V10.5zM8.25 6h7.5v2.25h-7.5V6zM12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25z"></path>',
}
</script>
