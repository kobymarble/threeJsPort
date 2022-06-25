
<template>
  <div class="h-screen px-6 py-12 bg-black">
    <h2
      id="title"
      class="font-2p text-5xl opacity-0 py-3 bg-gradient-to-r text-transparent bg-clip-text from-purple-400 to-red-500"
      style="transform: translateY(30px)"> Welcome
      </h2>
   
      
    <div class="flex py-4">
      <nuxt-link to="/about">
      <div id="about" class="px-4 text-white font-space-mono text-md opacity-0 hover:text-blue-300">About
        
          <img
            src="~assets/gameboy.jpg"
            alt="car"
            style="height: 70vh; width: 30vw"
            class="object-cover hover:opacity-80"
          />
          </div>
        </nuxt-link>
     
      <div >
        <nuxt-link to="/projects">
      <div id="about" class="px-4 text-white font-space-mono text-md opacity-0 hover:text-purple-300">Projects
        
          <img
            src="~assets/sega.jpg"
            alt="car"
            style="height: 70vh; width: 30vw"
            class="object-cover hover:opacity-80"
          />
          </div>
        </nuxt-link>
      </div>
      <div class="px-4">
       <nuxt-link to="/contact">
      <div id="about" class="px-4 text-white font-space-mono text-md opacity-0 hover:text-green-300">Contact
        
          <img
            src="~assets/phone.jpg"
            alt="car"
            style="height: 70vh; width: 30vw"
            class="object-cover hover:opacity-80"
          />
          </div>
        </nuxt-link>
        </div>
      <div>
       <nuxt-link to="/resume">
      <div id="about" class="px-4 text-white font-space-mono text-md opacity-0 hover:text-red-300">Resume
        
          <img
            src="~assets/hand.jpg"
            alt="car"
            style="height: 70vh; width: 30vw"
            class="object-cover hover:opacity-80"
          />
      </div>
       </nuxt-link>
        </div>
        </div>
        <Footer/>
  </div>

        
    
    
 
    
</template>

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

<script>
import gsap from "gsap";


import phoneImg from "~/assets/phone.jpg";

export default {
  data() {
    return {
      projects: [
        

        
          
        {
          image: {
            url: phoneImg,
          },
          title: "Contact",
        },
      ],
    };
  },
  mounted() {
    gsap.to("#title", {
      opacity: 1,
      duration: 2,
      y: 0,
      ease: "expo",
    });
    gsap.to("#about", {
      opacity: 1,
      duration: 2,
      stagger: 0.1,
      x: 0,
      ease: "expo",
      delay: 0.2,
    });
    gsap.to("#projects", {
      opacity: 1,
      duration: 2,
      stagger: 0.1,
      x: 0,
      ease: "expo",
      delay: 0.2,
    });
    gsap.to("#contact", {
      opacity: 1,
      duration: 2,
      stagger: 0.1,
      x: 0,
      ease: "expo",
      delay: 0.2,
    });
  },
};
</script>
