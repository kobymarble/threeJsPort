<template>
    <div class="bg-black h-screen px-6 py-12 pl-20 pr-20">
        <div class="flex justify-between px-20">
        <h2 class="font-2p text-5xl bg-gradient-to-r text-transparent bg-clip-text from-green-400 to-blue-500">About</h2> 
        <Nav/>
        </div>
        <div>
            <p class="font-space-mono text-white my-7 pl-20 pr-20">Hi. My name is Koby Marble. I'm from a dilapidated railroad town in upstate New York,
                and the majority of my working life has been spent as a butcher. Over time I became tired of having 
                my clothes be ruined by animal viscera, so I decided to begin teaching myself javascript in hopes of obtaining a new skill that would help me escape my current work. After some time of self teaching
                I enrolled in Burlington Code Academy in order to hone my coding skills. After months of learning the MERN stack, and graduating the course I was once again thrusted into the lonely world of self study. I have since returned to the cold and lonely world of 
                Upon re-entering this cold desolate realm I discovered I'm now eager to learn new technologies and move around their complexities much more nimbly. I have recently become quite enamored with webGl and ThreeJs and I am rapidly consuming as much as I can so this page can one day have a spinning 3d scan of my head.
            </p>
        </div>
        <div class="flex justify-center">
    <div class="text-white font-space-mono">
      <img style="height: 40vh; width: 32vw" src="~/assets/pixelKoby3.png"/>
    
    </div>
    </div>
        <Footer/>
    </div>
    
    
</template>

<script>
    export default {
        
    }
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

