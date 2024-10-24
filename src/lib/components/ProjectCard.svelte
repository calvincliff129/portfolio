<script lang="ts">
  export let index;
  export let project;
</script>

<div
  class="grid grid-cols-1 md:grid-cols-2 gap-8 md:gap-10 lg:gap-14 relative text-base max-lg:place-items-center"
>
  <div
    class={"flex flex-col gap-8 md:gap-10 pt-8 sm:pt-10 " +
      (index % 2 === 1 ? " md:order-2" : " ")}
  >
    <h4
      class="text-2xl sm:text-3xl md:text-4xl max-w-[1000px] w-full font-medium relative pr-10
        after:absolute after:top-full after:left-0 after:w-1/5 after:h-1.5 after:mt-1 after:bg-slate-800"
    >
      <slot />
    </h4>
    <p class="uppercase font-medium tracking-widest">
      ✦ {project.name} ✦
    </p>
    <div class="flex flex-col gap-3">
      {#each project.featureList as listItem}
        <div class="flex gap-2 items-center">
          <div
            class="grid place-items-center px-1.5 text-xs sm:text-sm aspect-square rounded-full border-green-300"
          >
            <i class="fa-solid fa-bolt text-green-400"></i>
          </div>
          <p>{listItem}</p>
        </div>
      {/each}
    </div>
    <div
      class={"flex-1 pl-2 flex justify-between gap-4 items-center " +
        (index === 3 || index === 4 ? " hidden" : " ")}
    >
      <a
        href={project.href}
        target="_blank"
        class="mr-auto cursor-pointer hover:text-slate-950 duration-200 relative after:absolute after:top-0 after:right-full after:w-full after:h-full after:bg-white after:duration-200 hover:after:translate-x-full after:z-[-1] overflow-hidden"
      >
        <p class="relative z-4">Go to &rarr;</p>
      </a>
    </div>
  </div>
  <div
    class={"flex flex-col overflow-hidden rounded-b-lg rounded-t-xl " +
      (index % 2 === 1 ? " order-1" : " ")}
  >
    <div
      class="rounded-t-xl h-8 sm:h-10 bg-white opacity-40 px-3 flex items-center gap-2"
    >
      {#each [1, 2, 3] as index}
        <div
          class="rounded-full aspect-square w-2.5 sm:w-3 bg-indigo-300"
        ></div>
      {/each}
    </div>
    <div
      class="flex flex-col bg-violet-1000 gap-4 flex-1 p-2 justify-start lg:justify-center items-center"
    >
      <img
        class="rounded-lg blueShadow"
        src={project.imgUrl}
        alt="project-img"
      />
    </div>
  </div>
</div>
