<script lang="ts">
  import ProjectCard from "./ProjectCard.svelte";

  type WorkProject = {
    name: string;
    featureList: string[];
    description: string;
    imgUrl: string;
    href: string;
  };
  let limit: boolean = true;
  let projectsList: WorkProject[] = [
    {
      name: "Voculus",
      featureList: [
        "IT company website built with SvelteKit",
        "Delivers targeted content",
        "Enhances online presence",
      ],
      description: "",
      imgUrl: "assets/images/projects/voculus.png",
      href: "https://voculus.com.my/",
    },
    {
      name: "Nemo",
      featureList: [
        "Built with SvelteKit + AdonisJs",
        "Multi-role-based HR and Payroll System ",
        "Simplifies approval workflows",
        "Multiple business functions in one platform",
      ],
      description: "",
      imgUrl: "assets/images/projects/nemo.png",
      href: "https://mypsmv2.lkim.gov.my/",
    },
    {
      name: "Verify My Helper",
      featureList: [
        "Created with Blazor + .Net",
        "Provides access to a blacklist status of helpers",
        "Helps employers make informed hiring decisions",
      ],
      description: "",
      imgUrl: "assets/images/projects/helper.png",
      href: "https://verifymyhelper.com/",
    },
    {
      name: "Muraloca",
      featureList: [
        "Built with Angular + .NET",
        "Mural gallery and management web app",
        "Locates and stores mural information around the city",
      ],
      description: "",
      imgUrl: "assets/images/projects/muraloca-page-1.png",
      href: "",
    },
    {
      name: "Argus",
      featureList: [
        "Built with SvelteKit + .NET + SignalR",
        "Live monitoring of urban areas",
        "Smart city, asset/incident management, and analytics system",
        "Real-time decision-making through advanced analytics",
      ],
      description: "",
      imgUrl: "assets/images/projects/argus.png",
      href: "",
    },
  ];
</script>

<div
  class="flex flex-col gap-10 sm:gap-14 md:gap-24 flex-1 items-center justify-center pb-6 md:pb-10"
>
  <div class="flex flex-col gap-2 text-center">
    <h6 class="text-lg sm:text-xl md:text-2xl">
      A few of my creative projects
    </h6>
    <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
      Curious to <span class="poppins text-violet-400">see</span> my work?
    </h3>
  </div>
  {#each limit ? projectsList.slice(0, 2) : projectsList as project, index}
    <ProjectCard {project} {index}>
      {#if index === 0}
        Elevating IT presence with <span class="text-violet-400 font-medium"
          >targeted</span
        > content
      {:else if index === 1}
        Improves operational <span class="text-violet-400 font-medium"
          >transparency</span
        > and decision-making for HR teams
      {:else if index === 2}
        A platform for finding <span class="text-violet-400 font-medium"
          >trustworthy</span
        >, dependable helper
      {:else if index === 3}
        Boosts cultural <span class="text-violet-400 font-medium"
          >appreciation</span
        > and community engagement
      {:else}
        Tailored urban <span class="text-violet-400 font-medium"
          >monitoring
        </span>
        and analytics for better city
        <span class="text-violet-400 font-medium">oversight</span>
      {/if}
    </ProjectCard>
  {/each}
</div>
<button
  on:click={() => (limit = !limit)}
  class="mx-auto px-4 py-2 rounder-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
>
  <i class={"fa-solid " + (limit ? "fa-angles-down" : "fa-angles-up")}></i>
  <p>{limit ? "Show More" : "Show Less"}</p>
</button>
