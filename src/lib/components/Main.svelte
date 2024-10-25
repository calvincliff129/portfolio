<script lang="ts">
  import Product from "./Project.svelte";

  let contactLink: string = "https://www.linkedin.com/in/calvincliff2129";

  type Steps = {
    name: string;
    icon: string;
    href: string;
  }[];
  type Benefits = {
    name: string;
    description: string;
  }[];

  let benefits: Benefits = [
    {
      name: "A CS graduate, self-taught developer.",
      description: `While I earned my degree in computer science, my current expertise knowledge grows from diving deep into new languages, 
      frameworks, and web architecture on my own using online resources, and quickly became fascinated with the creativity and 
      problem-solving involved in developing innovative online experiences. - - continuous self-learning in areas that go far beyond my formal education.`,
    },
    {
      name: "Passionate about turning concepts into reality",
      description: `I love translating designs into clean, functional code. 
      Taking pride in making sure everything runs smoothly and efficiently, ensuring a seamless user experience that resonate with users.`,
    },
    {
      name: "A focused and process-oriented thinker",
      description: `I enjoy simplifying the complex, turning tangled problems into straightforward solutions that keep 
      projects flowing smoothly and deliver outstanding results.`,
    },
  ];
</script>

<main class="flex flex-col flex-1 p-4">
  <section
    id="introPage"
    class="grid grid-cols-1 md:grid-cols-2 gap-10 py-8 sm:py-14 place-items-center"
  >
    <div
      class="flex flex-col md:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
    >
      <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
        Hi! I'm <span class="text-violet-400 poppins">Calvin</span> Cliff.
        <br />Front-End
        <span class="poppins text-violet-400">Developer</span>
      </h2>
      <p class="text-base sm:text-lg md:text-xl">
        My <span class="text-violet-400">favourite tech</span> includes Typecripts
        (Sveltekit, Angular or NEXT.JS), and TailwindCSS!
      </p>
      <a
        href={contactLink}
        target="_blank"
        class="blueShadow mx-auto lg:mr-auto lg:ml-0 tex-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-2 group rounded-full bg-white text-slate-950 cursor-pointer"
      >
        <div
          class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
        />
        <h4 class="relative z-9">Get in touch &rarr;</h4>
      </a>
    </div>
    <object
      class="relative w-full shadow-2xl grid max-md:order-first max-md:max-w-[300px] max-md:max-h-[300px] max-w-[500px] max-h-[500px]"
      title="Profile"
      data="assets/images/man-developing-website-on-desk.svg"
    >
    </object>
  </section>
  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
    <Product />
  </section>
  <section
    id="about"
    class="py-20 pt-10 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
  >
    <div
      class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
    >
      <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        A bit <span class="poppins text-violet-400">about</span> me.
      </h3>
    </div>
    <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
      I am . . .
    </p>
    <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
      {#each benefits as benefit, index}
        <div class="flex gap-6 sm:gap-8">
          <p
            class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
          >
            0{index + 1}
          </p>
          <div class="flex flex-col gap-6 sm:gap-8">
            <h3 class="text-2xl sm:text-3xl md:text-5xl">
              {benefit.name}
            </h3>
            <p>{benefit.description}</p>
          </div>
        </div>
      {/each}
    </div>
    <!-- <h5 class="text-2xl sm:text-3xl font-semibold text-center poppins">
      The <span class="text-violet-400 poppins">Complete</span> Package
    </h5>
    <div
      class="flex flex-col overflow-x-auto gap-10 max-w-[800px] mx-auto w-full"
    >
      <table class="bg-white text-slate-700 rounded text-center">
        <thead class="border-b border-solid border-slate-200">
          <tr>
            <th />
            <th class="whitespace-nowrap p-2 px-4">Candidate #1</th>
            <th class="whitespace-nowrap p-2 px-4">Candidate #2</th>
            <th class="whitespace-nowrap p-2 px-4">Candidate #3</th>
            <th class="whitespace-nowrap bg-violet-700 text-white p-4 px-8"
              >Me</th
            >
          </tr>
        </thead>
        <tbody>
          <tr class="border-b border-solid border-slate-200">
            <td
              class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
              >Dedication</td
            >
            <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
          <tr class="border-b border-solid border-slate-200">
            <td
              class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
              >Critical Thought</td
            >
            <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
          <tr class="border-b border-solid border-slate-200">
            <td
              class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
              >Remote Work Environment</td
            >
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
          <tr class="border-b border-solid border-slate-200">
            <td
              class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
              >Programming Ability</td
            >
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
            <td><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="mx-auto -mt-12 italic sm:hidden opacity-50">
      <p>Scroll to see more &rarr;</p>
    </div> -->
  </section>
</main>
