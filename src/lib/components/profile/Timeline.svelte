<script>
  import { userProfile } from ".";
  import { ChevronUp } from "lucide-svelte";
</script>

<ol class="ordered-list">
  {#each userProfile.userHistory as history}
    <li class="mb-14 flex items-center">
      {#if history.blogs}
        <div class="blog-list-div">
          <div class="mr-4 md:whitespace-nowrap">
            <p class="text-xs font-normal text-[#7A9299]">
              {history.date}
            </p>
          </div>
          <div class="blog-list-dot"></div>
          <div class="flex md:flex-row flex-col gap-3">
            {#each history.blogs as blog}
              <div
                class="custom-div-shadow rounded-[13px] max-w-[344px] w-full"
              >
                <img
                  class="rounded-t-[12px]"
                  src={blog.image}
                  alt="blog cover"
                />
                <h3 class="text-sm font-normal p-6">
                  {blog.title}
                </h3>
              </div>
            {/each}
          </div>
        </div>
      {:else}
        <div class="flex flex-col w-full gap-y-4">
          <div class="relative -left-[0.9rem] w-full">
            <ChevronUp class="text-[#778FB1]" />
          </div>
          <div class="position-list-div">
            <div class="mr-4">
              <div
                class="flex flex-col items-end md:whitespace-nowrap text-end"
              >
                <img
                  class="w-12 h-12"
                  src={history.companyLogo}
                  alt="comapany logo"
                />
                <p class="text-base font-bold">{history.companyName}</p>
                <p class="text-xs font-normal text-[#7A9299]">
                  {history.companyLocation}
                </p>
                <p class="text-xs font-normal text-[#7A9299]">Joined</p>
                <p class="text-xs font-normal text-[#7A9299]">
                  {history.Joined}
                </p>
              </div>
            </div>
            <div class="position-list-dot"></div>
            <div
              class="custom-div-shadow w-full rounded-[13px] py-4 px-5 flex flex-col gap-4 justfy-center"
            >
              <p class="text-base md:text-xl font-bold">{history.position}</p>
              <p class="text-sm font-normal text-[#7A9299] align-middle">
                {history.type !== "" && history.location !== ""
                  ? `${history.type} . ${history.location}`
                  : `${history.type} ${history.location}`}
              </p>
            </div>
          </div>
        </div>
      {/if}
    </li>
  {/each}
</ol>
