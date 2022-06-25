<template>
  <div class="bg-black h-screen px-6 py-12">
    <div class="flex justify-between">
      <h2
        class="font-2p text-5xl bg-gradient-to-r text-transparent bg-clip-text from-purple-800 via-purple-300 to-blue-800 pl-20 pr-20"
      >
        Contact
      </h2>
      <Nav />
    </div>
    <div>
      <p
        class="text-white font-space-mono pl-20 pr-20 flex justify-center py-5"
      >
        Currently looking for contract or full time in New York or remote as a
        full stack developer. <br />If you have any questions feel free to reach
        out.
      </p>
      <div class="flex justify-center py-10">
        <a
          class="text-white font-space-mono hover:text-purple-300"
          href="mailto: kobymarble@gmail.com"
        >
          Contact
          <img
            class="hover:opacity-80 font-space-mono text-white"
            src="~/assets/computer.jpg"
          />
        </a>
      </div>
    </div>
    <div class="py-10">
      <Footer />
    </div>
  </div>
</template>

<script>
import Socials from "../components/Socials.vue";
export default {
  components: { Socials },
};
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
