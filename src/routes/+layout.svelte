<script lang="ts">
  import "../app.css";
  import Header from "$lib/components/Header.svelte";
  import Footer from "$lib/components/Footer.svelte";

  let y: number;
  let innerHeight: number = 0;
  let innerWidth: number = 0;

  function gotoTop() {
    document.body.scrollIntoView();
  }
</script>

<div
  class="relative flex flex-col mx-auto w-full text-sm sm:text-base min-h-screen"
>
  <div
    class={"fixed bottom-0 w-full duration-300 flex p-10 z-[10] " +
      (y > 0
        ? "opacity-full pointer-events-auto"
        : "opacity-0 pointer-events-none")}
  >
    <button
      on:click={gotoTop}
      class="ml-auto rounded-full aspect-square bg-slate-900 text-violet-400 px-3 sm:px-4 hover:bg-slate-800 cursor-pointer"
    >
      <i class="fa-solid fa-arrow-up grid place-items-center aspect-square"></i>
    </button>
  </div>
  <div class="flex flex-col mx-auto max-w-[1400px]">
  <Header {y} />
    <slot />
  </div>
  <Footer />
</div>

<svelte:window bind:scrollY={y} bind:innerHeight bind:innerWidth />
