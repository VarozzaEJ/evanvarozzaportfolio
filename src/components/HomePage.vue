<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const x = ref(50)
const y = ref(0)

function update(event) {
  x.value = event.pageX
  y.value = event.pageY
}

onMounted(() => window.addEventListener('mousemove', update))
onUnmounted(() => window.removeEventListener('mousemove', update))

</script>

<template>


  <div
    class="absolute bg-purple-700/15 rounded-full -translate-x-1/2 -translate-y-1/2 max-md:hidden pointer-events-none blur-3xl "
    :style="{
      left: x + `px`,
      top: y + `px`,
      width: '800px',
      height: `800px`
    }">
  </div>

  <section v-motion :initial="{
    y: 100,
    opacity: 0,
  }" :enter="{
    y: 0,
    opacity: 1,
    transition: {
      delay: 500,
      type: 'spring',
      stiffness: 100,
      damping: 17,
      mass: 2,
    },
  }" class=" h-screen w-screen md:px-12 px-4 lg:px-24 lg:flex selection:bg-cyan-300 text-white
    selection:text-cyan-900 lg:gap-4 tracking-wide">
    <div class=" lg:px-15 lg:sticky lg:top-0 lg:w-dvw lg:h-10 lg:pt-20 lg:pb-20 pb-0 pt-10 ">

      <div class="h-40 lg:h-auto">
        <section class=" text-5xl mb-5 font-bold">
          <div class="">
            <p class="text-slate-200 cursor-pointer">
              Evan Varozza
            </p>
          </div>
        </section>
        <div class="mb-4">
          <p class="text-slate-200 text-xl">Full-Stack Developer</p>
        </div>
        <div class="mb-20 text-slate-400">
          <p class="w-64">I build responsive, accessible, back and front-end websites.</p>
        </div>
        <div class="flex flex-col invisible lg:visible">
          <a class="group flex items-center py-3 " href="#about"><span
              class="nav-indicator mr-4 h-px w-8 bg-slate-600 transition-all group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200 motion-reduce:transition-none"></span><span
              class="nav-text text-xs font-bold uppercase tracking-widest text-slate-500 group-hover:text-slate-200 group-focus-visible:text-slate-200">About</span>
          </a>
          <!-- <a class="group flex items-center py-3 " href="#experience"><span
              class="nav-indicator mr-4 h-px w-8 bg-slate-600 transition-all group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200 motion-reduce:transition-none"></span><span
              class="nav-text text-xs font-bold uppercase tracking-widest text-slate-500 group-hover:text-slate-200 group-focus-visible:text-slate-200">Experience</span>
          </a> -->
          <a class="group flex items-center py-3 " href="#projects"><span
              class="nav-indicator mr-4 h-px w-8 bg-slate-600 transition-all group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200 motion-reduce:transition-none"></span><span
              class="nav-text text-xs font-bold uppercase tracking-widest text-slate-500 group-hover:text-slate-200 group-focus-visible:text-slate-200">Projects</span>
          </a>

        </div>
      </div>

      <div class="flex justify-center md:justify-start">
        <div class="card md:mb-0 my-8 ">
          <a class="social-link1" href="https://github.com/VarozzaEJ">
            <svg xmlns="http://www.w3.org/2000/svg" fill="#fff" height="1em" viewBox="0 0 496 512">
              <path
                d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3.3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5.3-6.2 2.3zm44.2-1.7c-2.9.7-4.9 2.6-4.6 4.9.3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3.7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3.3 2.9 2.3 3.9 1.6 1 3.6.7 4.3-.7.7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3.7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3.7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z">
              </path>
            </svg>
          </a>
          <a class="social-link2" href="https://www.linkedin.com/in/evan-varozza-521b78293/">
            <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512" fill="#fff">
              <path
                d="M100.28 448H7.4V148.9h92.88zM53.79 108.1C24.09 108.1 0 83.5 0 53.8a53.79 53.79 0 0 1 107.58 0c0 29.7-24.1 54.3-53.79 54.3zM447.9 448h-92.68V302.4c0-34.7-.7-79.2-48.29-79.2-48.29 0-55.69 37.7-55.69 76.7V448h-92.78V148.9h89.08v40.8h1.3c12.4-23.5 42.69-48.3 87.88-48.3 94 0 111.28 61.9 111.28 142.3V448z">
              </path>
            </svg> </a>

        </div>
      </div>
      <section>
        <div>

        </div>
      </section>
    </div>
    <div class="   text-slate-400 mx-0 lg:mx-0  lg:pt-20 pt-10">
      <p class="lg:hidden text-slate-100 mb-5">About</p>
      <p id="about" class="md:mb-8 mb-7">Hello! I’m Evan Varozza, a passionate software developer with a knack for
        crafting
        innovative
        and efficient
        solutions. With a background in Full-Stack Developement,
        <span class="text-slate-100 hover:text-blue-400">
          C#
        </span> ,
        <span class="text-slate-100 hover:text-green-400">
          Vue
        </span>
        ,
        TailWind, and
        <span class="text-slate-100 hover:text-purple-400">
          Bootstrap
        </span>
        ,
        I thrive on
        transforming complex challenges into intuitive, user-friendly
        experiences.
      </p>
      <p class="md:mb-8 mb-7">
        Here, you’ll find a curated collection of my projects that showcase my skills, creativity, and dedication to
        quality. From sleek, responsive web applications to robust backend systems, each piece in my portfolio
        reflects
        my commitment to excellence and my love for coding.
      </p>
      <p>
        Feel free to explore, and if you have any questions or opportunities for collaboration, don’t hesitate to
        <span class="">
          reach
          out through
          <a href="https://www.linkedin.com/in/evan-varozza-521b78293/"
            class="cursor-pointer text-slate-100 hover:text-purple-400">
            linkedin
          </a>
          or an email to
          <a href="mailto:VarozzaEJ@gmail.com" class="cursor-pointer text-slate-100 hover:text-purple-400">
            VarozzaEJ@gmail.com
          </a>
        </span>
        . Let’s build something amazing together!
      </p>
      <div class="lg:px-15 mt-20">
        <!-- <p id="experience" class="lg:hidden text-slate-100 mb-5">Experience</p> -->
        <!-- <div v-motion :initial="{
          opacity: 0,
          y: 100,
        }" :visible="{
          opacity: 1,
          y: 0,
        }"
          class="flex hover:bg-slate-50/10 lg:cursor-pointer flex-col rounded-lg bg-slate-900 text-surface  shadow-secondary-1 dark:bg-surface-dark dark:text-white md:max-w-xl md:flex-row">
          <p class="text-slate-400 ps-6 lg:ps-0">August 2024</p>
          <div class="flex flex-col justify-start p-6">
            <h5 class="mb-2 text-xl font-medium cursor-pointer hover:text-purple-400">Card title</h5>
            <p class="mb-4 text-base">
              This is a wider card with supporting text below as a natural lead-in
              to additional content. This content is a little bit longer.
            </p>
            <p class="text-xs text-surface/75 dark:text-neutral-300">
              Last updated 3 mins ago
            </p>
          </div>
        </div> -->
        <p class="lg:hidden text-slate-100 my-5">Projects</p>
        <div id="projects" class="">
          <ol class="">
            <li v-motion :initial="{
              opacity: 0,
              y: 100,
            }" :visible="{
              opacity: 1,
              y: 0,
            }">

              <div
                class="flex mb-5 hover:bg-slate-50/10 hover:text-purple-400 transition-all ease-in-out delay-0 hover:-translate-y-1 hover:backdrop-blur-sm hover:blur-none  gap-4 flex-col-reverse items-start ps-3 pt-2 lg:p-0 lg:ps-2 lg:items-center justify-start md:justify-center rounded-lg bg-slate-900 text-surface shadow-secondary-1 dark:bg-surface-dark dark:text-white lg:hover:!opacity-100 lg:group-hover/list:opacity-50 lg:flex-row">

                <img class="h-40 lg:h-32 lg:pe-3 lg:w-72 w-52 pb-3 lg:py-3" src="/src/components/keepr.png" alt="">
                <div class="flex flex-col w-full">
                  <a class="lg:cursor-pointer" href="https://keepr.evanvarozza.dev/#/">
                    <p class="flex mt-2">Keepr <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                        stroke-width="1.5" stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                          d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                      </svg></p>
                  </a>
                  <p class="text-slate-400 pe-1">Keepr is a social site where you post "keeps" and save them into
                    "vaults".
                    Made
                    using a c# backend and vue front end, this app incorporates data manipulation using MySQL and
                    Dapper.
                  </p>
                  <div class="flex my-3">
                    <span
                      class="bg-green-100  text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-11">Vue</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-8">c#</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-15">MySQL</span>
                  </div>
                </div>
              </div>
            </li>
            <li v-motion :initial="{
              opacity: 0,
              y: 100,
            }" :visible="{
              opacity: 1,
              y: 0,
            }">

              <div
                class="flex mb-5 hover:bg-slate-50/10 hover:text-purple-400 transition-all ease-in-out delay-0 hover:-translate-y-1 hover:backdrop-blur-sm hover:blur-none  gap-4  flex-col-reverse items-start ps-3 pt-2 lg:p-0 lg:ps-2 lg:items-center justify-start md:justify-center rounded-lg bg-slate-900 text-surface shadow-secondary-1 dark:bg-surface-dark dark:text-white lg:hover:!opacity-100 lg:group-hover/list:opacity-50 lg:flex-row">

                <img class=" h-40 lg:h-32 lg:pe-3 lg:w-72 w-52 pb-3 lg:py-3" src="/src/components/tower.png" alt="">
                <div class="flex flex-col w-full">
                  <a class="lg:cursor-pointer" href="https://tower.evanvarozza.dev/#/">
                    <p class="flex mt-2">Tower<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                        stroke-width="1.5" stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                          d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                      </svg></p>
                  </a>
                  <p class="text-slate-400 pe-2">Tower simplifies event planning with an intuitive platform for
                    creating, managing, and promoting events. Enjoy features like customizable pages, easy RSVP
                    tracking, and real-time analytics to ensure your event’s success. Elevate your event experience with
                    Tower.
                  </p>
                  <div class="flex my-3">
                    <span
                      class="bg-green-100  text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-11">Vue</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-18">NodeJS</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-15">MongoDB</span>
                  </div>
                </div>
              </div>
            </li>
            <li v-motion :initial="{
              opacity: 0,
              y: 100,
            }" :visible="{
              opacity: 1,
              y: 0,
            }">

              <div
                class="flex mb-5 hover:bg-slate-50/10 hover:text-purple-400 transition-all ease-in-out delay-0 hover:-translate-y-1 hover:backdrop-blur-sm hover:blur-none  gap-4  flex-col-reverse items-start ps-3 pt-2 lg:p-0 lg:ps-2 lg:items-center justify-start md:justify-center rounded-lg bg-slate-900 text-surface shadow-secondary-1 dark:bg-surface-dark dark:text-white lg:hover:!opacity-100 lg:group-hover/list:opacity-50 lg:flex-row">

                <img class=" h-40 lg:h-32 lg:pe-3 lg:w-72 w-52 pb-3 lg:py-3" src="/src/components/SkyPulse.png" alt="">
                <div class="flex flex-col w-full">
                  <a class="lg:cursor-pointer" href="https://skypulse-one.vercel.app/">
                    <p class="flex mt-2">SkyPulse<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                        stroke-width="1.5" stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                          d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                      </svg></p>
                  </a>
                  <p class="text-slate-400 pe-2">Sky Pulse is a lightweight Weather app using Open-Meteo's and Open
                    Weather's forecast API's. This project was built in React 18, it incorporates use with many
                    different packages including Framer Motion, Bootstrap, and Axios.
                  </p>
                  <div class="flex my-3">
                    <span
                      class="bg-green-100  text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-18">React</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-18">Axios</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-15">Bootstrap</span>
                  </div>
                </div>
              </div>
            </li>
            <li v-motion :initial="{
              opacity: 0,
              y: 100,
            }" :visible="{
              opacity: 1,
              y: 0,
            }">

              <div
                class="flex mb-5 hover:bg-slate-50/10 hover:text-purple-400 transition-all ease-in-out delay-0 hover:-translate-y-1 hover:backdrop-blur-sm hover:blur-none  gap-4  flex-col-reverse items-start ps-3 pt-2 lg:p-0 lg:ps-2 lg:items-center justify-start md:justify-center rounded-lg bg-slate-900 text-surface shadow-secondary-1 dark:bg-surface-dark dark:text-white  lg:hover:!opacity-100 lg:group-hover/list:opacity-50 lg:flex-row">

                <img class="h-40 lg:h-32 lg:pe-3 lg:w-72 w-52 pb-3 lg:py-3" src="/src/components/jot.png" alt="">
                <div class="flex flex-col w-full">
                  <a class="lg:cursor-pointer" href="https://varozzaej.github.io/jot/">
                    <p class="flex mt-2">Jot<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                        stroke-width="1.5" stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                          d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                      </svg></p>
                  </a>
                  <p class="text-slate-400 pe-2">
                    Jot is your go-to note-taking platform for capturing ideas and staying organized. With its clean,
                    easy-to-navigate design, you can swiftly jot down thoughts, create structured notes, and manage
                    tasks. Simplify your workflow and keep your ideas in check with Jot—where clarity meets convenience.
                  </p>
                  <div class="flex my-3">
                    <span
                      class="bg-green-100  text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-22">Javascript</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-12">CSS</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-15">HTML</span>
                  </div>
                </div>
              </div>
            </li>
            <li v-motion :initial="{
              opacity: 0,
              y: 100,
            }" :visible="{
              opacity: 1,
              y: 0,
            }">

              <div
                class="flex mb-5 hover:bg-slate-50/10 hover:text-purple-400 transition-all ease-in-out delay-0 hover:-translate-y-1 hover:backdrop-blur-sm  hover:blur-none   gap-4 flex-col-reverse ps-3 pt-2 lg:p-0 lg:ps-2 items-start lg:items-center lg:hover:!opacity-100 lg:group-hover/list:opacity-50 justify-start md:justify-center rounded-lg bg-slate-900 text-surface shadow-secondary-1 dark:bg-surface-dark lg:-inset-x-6 lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg dark:text-white lg:flex-row">

                <img class="h-40 lg:h-32 lg:pe-3 lg:w-72 w-52 pb-3 lg:py-3" src="/src/components/petworks.png" alt="">
                <div class="flex flex-col w-full">
                  <a class="lg:cursor-pointer" href="https://boisepetworks.org/#/">

                    <p class="flex mt-2">Petworks<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                        stroke-width="1.5" stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                          d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                      </svg></p>
                  </a>
                  <p class="text-slate-400 pe-2">Petworks is the perfect place for pet lovers to create profiles for
                    their
                    pets, share updates and photos, and connect with other pet enthusiasts. Celebrate your pets and join
                    a community that’s as passionate about animals as you are!
                  </p>
                  <div class="flex my-3">
                    <span
                      class="bg-green-100  text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-11">Vue</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-18">NodeJS</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-15">MongoDB</span>
                  </div>
                </div>
              </div>
            </li>
            <li v-motion :initial="{
              opacity: 0,
              y: 100,
            }" :visible="{
              opacity: 1,
              y: 0,
            }">

              <div
                class="flex mb-5 hover:bg-slate-50/10 hover:text-purple-400 transition-all ease-in-out delay-0 hover:-translate-y-1 hover:backdrop-blur-sm  hover:blur-none  gap-4  flex-col-reverse ps-3 pt-2 lg:p-0 lg:ps-2 items-start lg:items-center lg:hover:!opacity-100 lg:group-hover/list:opacity-50 justify-start md:justify-center rounded-lg bg-slate-900 text-surface shadow-secondary-1 dark:bg-surface-dark lg:-inset-x-6 lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg dark:text-white lg:flex-row">

                <img class="h-40 lg:h-32 lg:pe-3 lg:w-72 w-52 pb-3 lg:py-3" src="/src/components/balloonpop.png" alt="">
                <div class="flex flex-col w-full">
                  <a class="lg:cursor-pointer" href="https://varozzaej.github.io/">

                    <p class="flex mt-2">Balloon Pop<svg xmlns="http://www.w3.org/2000/svg" fill="none"
                        viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                          d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                      </svg></p>
                  </a>
                  <p class="text-slate-400 pe-2">Balloon Pop is a fast-paced, addictive web app where the goal is
                    simple: pop
                    as many balloons as you can before time runs out! Test your reflexes and see how quickly you can
                    burst colorful balloons in this fun and challenging game.
                  </p>
                  <div class="flex my-3">
                    <span
                      class="bg-green-100  text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-22">Javascript</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-12">CSS</span>
                    <span
                      class="bg-green-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded-full dark:bg-green-900 dark:text-green-300 w-15">HTML</span>
                  </div>
                </div>
              </div>
            </li>

          </ol>

        </div>
        <footer class="max-w-md lg:pb-16 text-sm text-slate-500 pb-0">
          <span class="">Loosely designed in
            <a href="https://figma.com"
              class="font-medium text-slate-400 hover:text-purple-400 focus-visible:text-purple-400" target="_blank"
              aria-label="Figm (opens in a new tab)">
              Figma
            </a>
            and coded in
            <a href="https://code.visualstudio.com/"
              class="font-medium text-slate-400 hover:text-purple-400 focus-visible:text-purple-400" target="_blank"
              aria-label="Visual Studio Code (opens in a new tab)">
              Visual Studio Code
            </a>
            by yours truly. Built with
            <a href="https://vuejs.org"
              class="font-medium text-slate-400 hover:text-purple-400 focus-visible:text-purple-400"
              aria-label="VueJs (opens in a new tab)" target="_blank">
              Vue
            </a>
            and
            <a href="https://tailwindcss.com/" aria-label="tailwind css (opens in a new tab)" target="_blank"
              class="font-medium text-slate-400 hover:text-purple-400 focus-visible:text-purple-400">
              Tailwind CSS
            </a>
            , deployed with
            <a href="https://vercel.com/" aria-label="vercel (opens in new tab)" target="_blank"
              class="font-medium text-slate-400 hover:text-purple-400 focus-visible:text-purple-400">
              Vercel
            </a>
            . All text is set in the
            <a href="https://rsms.me/inter/"
              class="font-medium text-slate-400 hover:text-purple-400 focus-visible:text-purple-400"
              aria-label="inter typeface (opens in new tab)" target="_blank">
              Inter typeface.
            </a>
          </span>
        </footer>
      </div>
    </div>
  </section>

</template>

<style scoped>
.card {
  display: flex;
  justify-content: space-around;
  height: 30px;
  width: 200px;
}

.card svg {
  position: absolute;
  display: flex;
  width: 60%;
  height: 100%;
  font-size: 24px;
  font-weight: 700;
  opacity: 1;
  transition: opacity 0.25s;
  z-index: 2;
  cursor: pointer;
}

.card .social-link1,
.card .social-link2,
.card .social-link3,
.card .social-link4 {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 25%;
  color: whitesmoke;
  font-size: 24px;
  text-decoration: none;
  transition: 0.25s;
  border-radius: 50px;
}

.card svg {
  transform: scale(1);
}

.card .social-link1:hover {
  background-color: #1a1e22;
  animation: bounce_613 0.4s linear;
}

.card .social-link2:hover {
  background-color: #0a66c2;
  animation: bounce_613 0.4s linear;
}

.card .social-link3:hover {
  background-color: #0059f7;
  animation: bounce_613 0.4s linear;
}

.card .social-link4:hover {
  background-color: #1d4292;
  animation: bounce_613 0.4s linear;
}

@keyframes bounce_613 {
  40% {
    transform: scale(1.4);
  }

  60% {
    transform: scale(0.8);
  }

  80% {
    transform: scale(1.2);
  }

  100% {
    transform: scale(1);
  }
}
</style>
