<template>
  <div class="bg-black px-6 py-12">
    <div class="flex justify-between pr-20 pl-20">
      <h2
        class="font-2p text-5xl bg-gradient-to-r text-transparent bg-clip-text from-purple-400 to-red-500"
      >
        Resume
      </h2>

      <Nav />
    </div>

    <div class="font-space-mono text-white pr-20 pl-20 text 3-xl">
      <div class="flex justify-center">
        <ul class="text-lg">
          <li>Oneonta, Ny</li>
          <li>(607)267-0416</li>
          <li>Kobymarble@gmail.com</li>
          <li>LinkedIn/in/koby-marble</li>
          <li>Github.com/kobymarble</li>
        </ul>
      </div>
      <h1 class="underline text-2xl py-2">Objective:</h1>
      <p>
        Determined and focused developer with a passion for creating inventive
        solutions for innovative companies. Developed a web app for tracking
        patients’ health issues, designed shipping confirmation email, and am
        currently building an ecommerce store for a glassware shop. Very
        interested in digital art and currently creating a program to make
        AI-generated art while not putting stress on Best Buy’s servers using
        bots I made with Puppeteer.
      </p>
      <h1 class="py-2 font-bold italic">Education & Certifications:</h1>
      <ul>
        <li>● Burlington Code Academy, Burlington, VT, December 2021</li>
        <li class="px-4">
          ○ 480+ hours of coding, Full-stack development, client-side
          programming, server-side coding, and product management (MERN)
        </li>
      </ul>
      <h1 class="text-2xl underline py-2">Technical Skills & Competencies:</h1>

      <strong class="font-bold italic"> Technical Skills: </strong>JavaScript,
      React, HTML, CSS, Git, MongoDB, Firebase, Puppeteer,Agile, Scrum.<br />
      <strong class="bold italic">Competencies:</strong> Project management,
      working with clients, communication, collaboration, teamwork, leadership.
      <h1 class="2xl italic">Technical Projects:</h1>
      For our capstone project we made a fully functional crud app while using
      the principles of agile development, and were able to put those principles
      to practice while spending the final month of the bootcamp developing the
      project for a burlington tech figurehead.
      <a href="https://bca-poop.herokuapp.com/"
        >https://bca-poop.herokuapp.com/</a
      >
      <h1 class="underline text-2xl py-2">Professional Experience:</h1>
      <h2 class="font-bold italic">
        Web Developer, Rajin Tech, Albany, New York, December 2021 - Present
      </h2>
      <ul>
        <li>
          ● Full stack development of an ecommerce store for a glassware
          company.
        </li>
        <li>
          ● Utilizing HTML, CSS, React, Node, and Firebase to build the
          application.
        </li>
        <li>
          ● Being the sole developer of this site furthered my abilities in
          constructing a React application while
        </li>
        <li>
          pushing my creativity to work in tandem with the client's vision.
        </li>
      </ul>
      <h2 class="font-bold italic py-2">
        Assistant Meat Manager, Price Chopper, Colchester, VT, June 2010 - July
        2021
      </h2>
      <ul>
        <li>
          ● Responsible for maintaining the functionality of a department of 5
          people
        </li>
        <li>
          ● Oversaw the ordering of the product for the daily shipments and the
          scheduling of associates
        </li>
        <li>
          ● Developed strong leadership skills while cultivating a strong team
          culture as well as matured skills in multitasking, time management,
          resourcefulness, and teamwork
        </li>
      </ul>
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
