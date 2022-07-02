<template>
  <div class="bg-black h-screen px-6 py-12 pl-20 pr-20">
    <div class="flex justify-between px-20">
      <h2
        class="font-2p text-5xl bg-gradient-to-r text-transparent bg-clip-text from-green-400 to-blue-500"
      >
        About
      </h2>
      <Nav />
    </div>
    <div>
      <p class="font-space-mono text-white my-7 pl-20 pr-20">
        I'm Koby Marble. I'm from a dilapidated railroad town in
        upstate New York, and the majority of my working life has been spent as
        a butcher. Over time, ruining my clothes with
        animal viscera got old, so I decided to begin teaching myself javascript in
        order to learn coding skills that would help me escape my current
        reality. I enrolled in Burlington Code
        Academy for real work experience in the field and exposure working collaboratively on projects. After months of learning the
        MERN stack, and graduating the course I was thrust back into the
        lonely world of self study. Upon re-entering this cold desolate realm I realized I'm
        eager to to compound my knowledge, learn new technologies, and move around their complexities
        more nimbly. I have recently become quite enamored with webGl and
        ThreeJs and I'm rapidly consuming as much as I can so this page can one
        day have a spinning 3d scan of my head.
      </p>
    </div>
    <div class="flex justify-center">
      <div class="text-white font-space-mono">
        <img style="height: 40vh; width: 32vw" src="~/assets/pixelKoby3.png" />
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
