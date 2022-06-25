<template>
  <div class="bg-black px-6 py-12 h-screen">
    <div class="flex justify-between">
      <h2
        class="font-2p text-5xl bg-gradient-to-r text-transparent bg-clip-text from-blue-500 to-purple-500"
      >
        Projects
      </h2>

      <Nav />
    </div>

    <div class="flex py-4">
      <div class="px-4">
        <a href="https://bca-poop.herokuapp.com/">
          <img
            src="~assets/poop.png"
            alt="car"
            style="height: 70vh; width: 60vw"
            class="object-cover hover:opacity-80"
          />
          <p id="about" class="text-white font-space-mono text-sm">
            Post Operation Observation Project
          </p>
        </a>
        <div class="py-3">
          <a
            class="font-space-mono text-white py-3 hover:text-blue-200"
            href="https://github.com/burlingtoncodeacademy-students/POOP"
          >
            Source Code</a
          >
        </div>
      </div>
      <div>
        <a href="https://kobys-fightinggame.netlify.app/">
          <img
            src="~assets/fighting.png"
            alt="car"
            style="height: 70vh; width: 60vw"
            class="object-cover hover:opacity-80"
          />
          <p id="projects" class="text-white font-space-mono text-sm">
            Script Fighter 2
          </p>
        </a>
        <div class="py-3">
          <a
            class="font-space-mono text-white hover:text-purple-200"
            href="https://github.com/kobymarble/fighting-game"
          >
            Source Code
          </a>
        </div>
      </div>
    </div>
    <Footer />
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
