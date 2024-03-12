<script>
  import { userProfile } from ".";
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import Button from "../ui/button/button.svelte";
  import MyWebsiteIcon from "$lib/icons/MyWebsiteIcon.svelte";
  import DotsIcons from "$lib/icons/DotsIcons.svelte";

  let isClicked = false;

  const handleClick = () => {
    isClicked = !isClicked;
  };
</script>

<div
  class="mt-12 mx-4 lg:mx-[291px] flex gap-x-7 lg:gap-x-14 flex-wrap lg:flex-nowrap gap-y-16 justify-center"
>
  <div
    class="w-[90px] lg:w-[120px] h-[90px] lg:h-[120px] text-center flex flex-col gap-y-1"
  >
    <Avatar.Root
      class="aspect-ratio border-[5px] border-[#EAEFF5] w-[90px] lg:w-[120px] h-[90px] lg:h-[120px]"
    >
      <Avatar.Image src={userProfile.profileImage} alt="@shadcn" />
      <Avatar.Fallback>CN</Avatar.Fallback>
    </Avatar.Root>

    <h2 class="font-bold lg:leading-7 lg:text-2xl text-base text-[#4B5C6D]">
      {userProfile.name}
    </h2>
  </div>
  <div
    class="flex items-center justify-center lg:justify-between gap-y-12 lg:gap-x-52 flex-wrap lg:flex-nowrap text-center lg:text-start"
  >
    <div
      class="flex flex-col items-center lg:items-start text-[#141618] text-sm leading-6 font-normal gap-y-[1.875rem]"
    >
      <p>
        {userProfile.description}
      </p>
      <Button
        variant="outline"
        class="button custom-btn-shadow hover:bg-white hover:text-[#4D4D4D] lg:hover:bg-[#0066FF] lg:hover:text-white rounded-[4px] px-6 py-2 gap-x-2"
        on:click={handleClick}
      >
        {isClicked ? "Followed" : "Follow"}
      </Button>
    </div>
    <div class="flex flex-col gap-y-2 lg:gap-y-[1.875rem]">
      <div
        class="flex flex-col items-center text-center lg:items-end lg:text-end"
      >
        <img class="pb-2" src={userProfile.companyLogo} alt="company logo" />
        <p class="text-base font-bold">
          {userProfile.companyName}
        </p>
        <p class="text-[#7A9299] font-normal text-xs">
          {userProfile.position}
        </p>
      </div>
      <div class="flex items-center">
        <a href={userProfile.website} target="_blank">
          <Button
            variant="ghost"
            class="gap-x-2 text-[#4D4D4D] font-normal hover:bg-white hover:text-[#4D4D4D]"
          >
            My website <MyWebsiteIcon />
          </Button>
        </a>
        <DotsIcons />
      </div>
    </div>
  </div>
</div>

