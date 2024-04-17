---
title: Example report
---

# A brief history of space exploration

This report is a brief overview of the history and current state of rocket launches and space exploration.

```js echo
// import * as THREE from "npm:three";
import * as THREE from "three";

const height = 300;
const camera = new THREE.PerspectiveCamera(70, width / height, 0.01, 10);
const scene = new THREE.Scene();
const geometry = new THREE.BoxGeometry(0.2, 0.2, 0.2);
const material = new THREE.MeshNormalMaterial();
const mesh = new THREE.Mesh(geometry, material);
const renderer = new THREE.WebGLRenderer({antialias: true});
camera.position.z = 1;
scene.add(mesh);

const animation = (time) => {
  mesh.rotation.x = time / 2000;
  mesh.rotation.y = time / 1000;
  renderer.render(scene, camera);
};

renderer.setSize(width, height);
renderer.setAnimationLoop(animation);
display(renderer.domElement);
```


## Background

<div>
    <canvas class="webgl"></canvas>
</div>

```js echo
// import './style.css'
// import * as THREE from 'three'
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'

/**
 * Base
 */
// Canvas
const canvas = document.querySelector('canvas.webgl')

// Scene
const scene = new THREE.Scene()

/**
 * Sizes
 */

// const width = 500
const height = 500

// const sizes = {
//     width: window.innerWidth,
//     height: window.innerHeight
// }

// window.addEventListener('resize', () => {
//     // Update sizes
//     sizes.width = window.innerWidth
//     sizes.height = window.innerHeight
//
//     // Update camera
//     camera.aspect = sizes.width / sizes.height
//     camera.updateProjectionMatrix()
//
//     // Update renderer
//     renderer.setSize(sizes.width, sizes.height)
//     renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))
// })

/**
 * Camera
 */
// Base camera
// const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height, 0.1, 100)
const camera = new THREE.PerspectiveCamera(75, width / height, 0.1, 100)
camera.position.x = 1
camera.position.y = 1
camera.position.z = 1
scene.add(camera)

// Controls
const controls = new OrbitControls(camera, canvas)
controls.enableDamping = true

/**
 * Cube
 */
const cube = new THREE.Mesh(
    new THREE.BoxGeometry(1, 1, 1),
    new THREE.MeshBasicMaterial({ color: 0xff0000 })
)
scene.add(cube)

/**
 * Renderer
 */
const renderer = new THREE.WebGLRenderer({
    canvas: canvas,
    antialias: true,
})
// renderer.setSize(sizes.width, sizes.height)
renderer.setSize(width, height)
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))

/**
 * Animate
 */
const clock = new THREE.Clock()
let lastElapsedTime = 0

const tick = () => {
    const elapsedTime = clock.getElapsedTime()
    const deltaTime = elapsedTime - lastElapsedTime
    lastElapsedTime = elapsedTime

    // Update controls
    controls.update()

    // Render
    renderer.render(scene, camera)

    // Call tick again on the next frame
    window.requestAnimationFrame(tick)
}

tick()
```

The history of rocket launches dates back to ancient China, where gunpowder-filled tubes were used as primitive forms of propulsion.

Fast-forward to the 20th century during the Cold War era, the United States and the Soviet Union embarked on a space race, a competition to innovate and explore beyond Earth.

This led to the launch of the first artificial satellite, Sputnik 1, and the crewed moon landing by Apollo 11. As technology advanced, rocket launches became synonymous with space exploration and satellite deployment.

## The Space Shuttle era

```js
import {timeline} from "./components/timeline.js";
```

```js
const events = FileAttachment("./data/events.json").json();
```

```js
timeline(events, {height: 300})
```

### Sputnik 1 (1957)

This was the first artificial satellite. Launched by the Soviet Union, it marked the beginning of the space age.

### Apollo 11 (1969)

The historic Apollo 11 mission, led by NASA, marked the first successful human landing on the Moon. Astronauts Neil Armstrong and Buzz Aldrin became the first humans to set foot on the lunar surface.

### Viking 1 and 2 (1975)

NASA’s Viking program successfully launched two spacecraft, Viking 1 and Viking 2, to Mars. These missions were the first to successfully land and operate on the Martian surface, conducting experiments to search for signs of life.

### Space Shuttle Columbia (1981)

The first orbital space shuttle mission, STS-1, launched the Space Shuttle Columbia on April 12, 1981. The shuttle program revolutionized space travel, providing a reusable spacecraft for a variety of missions.

### Hubble Space Telescope (1990)

The Hubble Space Telescope has provided unparalleled images and data, revolutionizing our understanding of the universe and contributing to countless astronomical discoveries.

### International Space Station (ISS) construction (1998—2011)

The ISS, a collaborative effort involving multiple space agencies, began construction with the launch of its first module, Zarya, in 1998. Over the following years, various modules were added, making the ISS a symbol of international cooperation in space exploration.

## Commercial spaceflight

After the Space Shuttle program, a new era emerged with a shift towards commercial spaceflight.

Private companies like Blue Origin, founded by Jeff Bezos in 2000, and SpaceX, founded by Elon Musk in 2002, entered the scene. These companies focused on developing reusable rocket technologies, significantly reducing launch costs.

SpaceX, in particular, achieved milestones like the first privately developed spacecraft to reach orbit (Dragon in 2010) and the first privately funded spacecraft to dock with the ISS (Dragon in 2012).

## Recent launch activity

The proliferation of commercial space companies has driven a surge in global launch activity within the last few years.

SpaceX’s Falcon 9 and Falcon Heavy, along with other vehicles from companies like Rocket Lab, have become workhorses for deploying satellites, conducting scientific missions, and ferrying crew to the ISS.

The advent of small satellite constellations, such as Starlink by SpaceX, has further fueled this increase in launches. The push for lunar exploration has added momentum to launch activities, with initiatives like NASA’s Artemis program and plans for crewed missions to the Moon and Mars.

## Looking forward

As technology continues to advance and global interest in space exploration grows, the future promises even more exciting developments in the realm of rocket launches and space travel.

Exploration will not only be limited to the Moon or Mars, but extend to other parts of our solar system such as Jupiter and Saturn’s moons, and beyond.
