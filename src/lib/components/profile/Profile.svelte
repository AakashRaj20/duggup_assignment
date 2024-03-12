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

<div class="mt-12 mx-[291px] flex gap-x-14">
  <div class="w-[120px] h-[120px] text-center flex flex-col gap-y-1">
    <Avatar.Root class="border-[5px] border-[#EAEFF5] w-[120px] h-[120px]">
      <Avatar.Image src={userProfile.profileImage} alt="@shadcn" />
      <Avatar.Fallback>CN</Avatar.Fallback>
    </Avatar.Root>

    <h2 class="font-bold leading-7 text-2xl text-[#4B5C6D]">
      {userProfile.name}
    </h2>
  </div>
  <div class="flex items-center justify-between gap-x-52">
    <div
      class="flex flex-col items-start text-[#141618] text-sm leading-6 font-normal gap-y-[1.875rem]"
    >
      <p>
        {userProfile.description}
      </p>
      <Button
        variant="outline"
        class="button custom-shadow hover:bg-[#0066FF] hover:text-white hover:border-[#0066FF]"
        on:click={handleClick}
      >
        {isClicked ? "Following" : "Follow"}
      </Button>
    </div>
    <div class="flex flex-col gap-y-[1.875rem]">
      <div class="flex flex-col items-end text-end">
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
          <Button variant="ghost" class="gap-x-2 text-[#4D4D4D] font-normal hover:bg-white hover:text-[#4D4D4D]">
            My website <MyWebsiteIcon />
          </Button>
        </a>
        <DotsIcons />
      </div>
    </div>
  </div>
</div>

<!-- <script>
            let isClicked = false;

            function handleClick() {
                isClicked = !isClicked;
            }
        </script>

        <button
            class={isClicked ? 'clicked' : 'not-clicked'}
            on:click={handleClick}
        >
            {isClicked ? 'Clicked!' : 'Click me'}
        </button>

        <style>
            .not-clicked {
                background-color: #4B5C6D;
                color: white;
                padding: 10px 20px;
                border: none;
                border-radius: 4px;
                cursor: pointer;
            }

            .clicked {
                background-color: #EAEFF5;
                color: #4B5C6D;
                padding: 10px 20px;
                border: none;
                border-radius: 4px;
                cursor: pointer;
            } -->
<!-- </style> -->
