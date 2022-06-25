<template>
<div>
    <canvas ref='canvas'></canvas>
      <div
        id="container"
        class="absolute text-white text-center w-full max-w-5xl px-6"
        style="top: 50%; transform: translate(-50%, -50%); left: 50%"
      >
        <h1
          id="kobymarble"
          class="font-space-mono text-sm uppercase tracking-wide opacity-0 py-5"
          style="transform: translateY(30px);"
        >
          Hi, Im Koby!
        </h1>
        <p id="meathell" 
        class="font-2p text-4xl opacity-0"
        style="transform: translateY(30px)"
        >
        Join my on my adventure <br>into full stack development
        </p>
        <button
          id="viewwork"
          class="border px-4 py-2 rounded-lg text-sm font-space-mono uppercase mt-8 hover:bg-white hover:text-gray-800 opacity-0"
          style="transform: translateY(30px)"
          >
          Engage Thrusters
        </button>
      </div>
      </div>
</template>

<script>
import {PlaneGeometry, BufferAttribute, Raycaster, Scene, PerspectiveCamera, 
WebGLRenderer, MeshPhongMaterial, DoubleSide, Mesh, DirectionalLight, BufferGeometry, PointsMaterial,
Float32BufferAttribute,Points, FlatShading} from 'three';
import OrbitControls from 'orbit-controls-es6';
import gsap from 'gsap'


export default {
  mounted(){
const dat = require('dat.gui')
const gui = new dat.GUI()
console.log(gui)
const world = {
  plane: {
    width: 400,
    height: 400,
    widthSegments: 50,
    heightSegments: 50
  }
}
gui.add(world.plane, 'width',1, 500).
onChange(generatePlane)
  
gui.add(world.plane, 'height',1, 500).
onChange(generatePlane)

gui.add(world.plane, 'heightSegments',1, 100).
onChange(generatePlane)

gui.add(world.plane, 'widthSegments',1, 100).
onChange(generatePlane)

function generatePlane() {
  planeMesh.geometry.dispose()
  planeMesh.geometry = new PlaneGeometry(
    world.plane.width,
    world.plane.height,
    world.plane.widthSegments,
    world.plane.heightSegments,
    )
    const {array} = planeMesh.geometry.attributes.position
    const randomValues =[]
    for(let i = 0; i < array.length; i++){
      
      if( i % 3 === 0){
      const x = array[i]
      const y = array[i + 1]
      const z = array[i + 2]
    
     array[i] = x + (Math.random() - 0.5) * 3
     array[i + 1] = y + (Math.random() - 0.5) * 3
     array[i + 2] = z + (Math.random()-0.5) *3
    }
     randomValues.push(Math.random() * Math.PI *2) 
    }
    planeMesh.geometry.attributes.position.randomValues = randomValues
    planeMesh.geometry.attributes.position.originalPosition =
    planeMesh.geometry.attributes.position.array
// initial color
const colors = []
for(let i = 0; i < planeMesh.geometry.attributes.position.count; i++){
  colors.push(.2,.3,.9)
}

// colors for vertices
planeMesh.geometry.setAttribute(
  'color', 
  new BufferAttribute(new
    Float32Array(colors), 3))
}

const raycaster = new Raycaster()
const scene = new Scene();
const camera = new PerspectiveCamera(75, 
  innerWidth / innerHeight, 0.1, 1000)

const renderer = new WebGLRenderer({
  canvas: this.$refs.canvas
})



renderer.setSize(innerWidth, innerHeight)
renderer.setPixelRatio(devicePixelRatio)



new OrbitControls(camera,renderer.domElement)
camera.position.z = 50

const planeGeometry = new PlaneGeometry(world.plane.width,world.plane.height,world.plane.widthSegments,world.plane.heightSegments)
const planeMaterial = new MeshPhongMaterial({

side: DoubleSide,
flatShading: FlatShading,
vertexColors: true
})
const planeMesh = new Mesh(planeGeometry,planeMaterial)
scene.add(planeMesh)
generatePlane()


const light = new DirectionalLight(
  0xffffff, 1
)
light.position.set(0,1,1)
scene.add(light)

const backLight = new DirectionalLight(
  0xffffff, 1
)
backLight.position.set(0,0,-1)
scene.add(backLight)

const starGeometry = new BufferGeometry()
const starMaterial = new PointsMaterial({
  color: 0xffffff
})

const starVerticies = []
for (let i = 0; i < 10000; i++) {
  const x = (Math.random() - 0.5) * 2000
  const y = (Math.random() - 0.5) * 2000
  const z = (Math.random() - 0.5) * 2000
  starVerticies.push(x, y, z)
}

console.log(starVerticies)

starGeometry.setAttribute(
  'position',
  new Float32BufferAttribute(starVerticies, 3)
)

console.log(starGeometry)
console.log(starMaterial)

const stars = new Points(starGeometry, starMaterial)
scene.add(stars)

const mouse = {
  x: undefined,
  y:  undefined
}

let frame = 0
function animate(){
  requestAnimationFrame(animate)
  renderer.render(scene, camera)
  raycaster.setFromCamera(mouse, camera)
  frame += 0.01


  const {array, originalPosition, randomValues} = planeMesh.geometry.attributes.position
  for (let i = 0; i < array.length; i += 3)
  {
    array[i] = originalPosition[i] + Math.cos(frame + randomValues[i]) * 0.001
    //  y coordinate
    array[i + 1] = originalPosition[i + 1] + Math.sin(frame + randomValues[i + 1]) * 0.001
    
  }
  planeMesh.geometry.attributes.position.needsUpdate = true

  const intersects = raycaster.
  intersectObject(planeMesh)
  if (intersects.length > 0){
    // change colors of veritices
    const {color} =  intersects[0].object.geometry.
    attributes
    // vertice 1
  color.setX(intersects[0].face.a,0.1)
  color.setY(intersects[0].face.a,0.5)
  color.setZ(intersects[0].face.a,1)
  //  vertice 2
  color.setX(intersects[0].face.b,0.1)
  color.setY(intersects[0].face.b,0.5)
  color.setZ(intersects[0].face.b,1)
  // vertice 3
  color.setX(intersects[0].face.c,0.1)
  color.setY(intersects[0].face.c,0.5)
  color.setZ(intersects[0].face.c,0.5)
   
  intersects[0].object.geometry.
    attributes.color.needsUpdate = 
    true

    const initialColor = {
      r:.02,
      g:.75,
      b:.68
    }
    const hoverColor = {
      r: 0.91,
      g:.30,
      b:.32
    }
    gsap.to(hoverColor, {
      r: initialColor.r,
      g:initialColor.g,
      b:initialColor.b,
      onUpdate: () => {
  color.setX(intersects[0].face.a,hoverColor.r)
  color.setY(intersects[0].face.a,hoverColor.g)
  color.setZ(intersects[0].face.a,hoverColor.b)
  //  vertice 2
  color.setX(intersects[0].face.b,hoverColor.r)
  color.setY(intersects[0].face.b,hoverColor.g)
  color.setZ(intersects[0].face.b,hoverColor.b)
  // vertice 3
  color.setX(intersects[0].face.c,hoverColor.r)
  color.setY(intersects[0].face.c,hoverColor.g)
  color.setZ(intersects[0].face.c,hoverColor.b)
  color.needsUpdate = true
      }
    })
  }
  stars.rotation.x += .0005
}


animate()



addEventListener('mousemove', (event) =>{
  mouse.x = (event.clientX / innerWidth) * 2 -1
  mouse.y = -(event.clientY / innerHeight) * 2 + 1
  
 
})

gsap.to('#kobymarble',{
  opacity: 1,
  duration: 1.5,
  y:0,
  ease:'expo'
})
gsap.to('#meathell',{
  opacity: 1,
  duration: 1.5,
  delay: 0.3,
  y:0,
  ease: 'expo'
})
gsap.to('#viewwork',{
  opacity: 1,
  duration: 1.5,
  delay: 0.6,
  y:0,
  ease: 'expo'
})

document.querySelector('#viewwork').
addEventListener('click',(e) => {
  e.preventDefault()
  gsap.to('#container',{
    opacity:0
  })


gsap.to(camera.position, {
  z: 25,
  ease: 'power3.inOut',
  duration: 2
})
gsap.to(camera.rotation,{
  x: 1.57,
  ease: 'power3.inOut',
  duration: 2
})
gsap.to(camera.position,{
  y: 1000,
  ease: 'power3.in',
  duration: 1,
  delay: 2,
  onComplete: () => {
   this.$router.push('/work')
  }
})
})

addEventListener('resize', () =>{
  camera.aspect = innerWidth / innerHeight
  camera.updateProjectionMatrix()

  renderer.setSize(innerWidth, innerHeight)
})
  }
}
</script>

<style>
body{
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

