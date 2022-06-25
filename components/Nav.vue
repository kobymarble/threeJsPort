<template>
  <div class="bg-black">
    <ul class="flex justify-center py-4">
      <div class="px-2">
        <li>
          <nuxt-link
            class="inline-block px-3 font-2p text-white border px-4 py-1 border-purple-700 rounded-lg text-sm hover:bg-purple-500 hover:text-yellow-500"
            to="/work"
            >Home</nuxt-link
          >
        </li>
      </div>
      <li>
        <nuxt-link
          class="inline-block px-3 font-2p text-white border px-4 py-1 border-purple-400 rounded-lg text-sm hover:bg-purple-400 hover:text-yellow-500"
          to="/projects"
          >Projects</nuxt-link
        >
      </li>
      <div class="px-2">
        <li>
          <nuxt-link
            class="inline-block px-3 font-2p border px-4 py-1 border-blue-300 rounded-lg text-sm text-white hover:bg-blue-300 hover:text-yellow-500"
            to="/resume"
            >Resume</nuxt-link
          >
        </li>
      </div>
      <div>
        <li>
          <nuxt-link
            class="inline-block px-3 font-2p border px-4 py-1 border-blue-400 rounded-lg text-sm text-white hover:bg-blue-500 hover:text-yellow-500"
            to="/about"
            >about</nuxt-link
          >
        </li>
      </div>
      <div class="px-2">
        <li>
          <nuxt-link
            class="inline-block px-3 font-2p border px-4 py-1 border-blue-800 rounded-lg text-sm text-white hover:bg-blue-800 hover:text-yellow-500"
            to="/contact"
            >contact</nuxt-link
          >
        </li>
      </div>
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style>
body {
  margin: 0;
  -webkit-font-smoothing: antialiased;
}
.font-2p {
  font-family: "Press Start 2P", cursive;
}
.font-space-mono {
  font-family: "Space Mono", monospace;
}
</style>
