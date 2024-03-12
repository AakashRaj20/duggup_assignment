<script lang="ts">
  import * as Sheet from "$lib/components/ui/sheet/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import { AlignJustify, ChevronDown } from "lucide-svelte";
  import DuggupLogo from "$lib/icons/DuggupLogo.svelte";
  import Home from "$lib/icons/Home.svelte";
  import Explore from "$lib/icons/Explore.svelte";
  import Learn from "$lib/icons/Learn.svelte";
  import Post from "$lib/icons/Post.svelte";
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
  import { userProfile } from "../profile";
</script>

<nav class="flex justify-between p-2 lg:hidden">
  <div class="flex gap-x-1">
    <DuggupLogo />
    <p class="text-xl font-bold text-[#333333]">duggup</p>
  </div>
  <Sheet.Root>
    <Sheet.Trigger asChild let:builder>
      <Button builders={[builder]} variant="ghost"><AlignJustify /></Button>
    </Sheet.Trigger>
    <Sheet.Content side="right" class="w-[300px]">
      <div class="flex flex-col gap-y-10 items-center mt-10">
        <div class="flex">
          <Avatar.Root class="border-[0.5px] border-[#4D4D4D]">
            <Avatar.Image src={userProfile.profileImage} alt="@shadcn" />
            <Avatar.Fallback>CN</Avatar.Fallback>
          </Avatar.Root>
          <DropdownMenu.Root>
            <DropdownMenu.Trigger asChild let:builder>
              <Button
                variant="ghost"
                class="text-[20px] font-medium text-[#4D4D4D] gap-x-3"
                builders={[builder]}>Krishna Kiran <ChevronDown /></Button
              >
            </DropdownMenu.Trigger>
            <DropdownMenu.Content class="w-56 p-4 gap-y-4 flex flex-col">
              <p>DashBoard</p>
              <p>Log Out</p>
            </DropdownMenu.Content>
          </DropdownMenu.Root>
        </div>
        <Button class="gap-x-2 text-[#4D4D4D] font-normal" variant="ghost">
          <Home />
          Home
        </Button>
        <Button class="gap-x-2 text-[#4D4D4D] font-normal" variant="ghost">
          <Explore />
          Explore
        </Button>
        <Button class="gap-x-2 text-[#4D4D4D] font-normal" variant="ghost">
          <Learn />
          Learn
        </Button>
        <Button
          class="custom-btn-shadow button focus:bg-white focus:text-[#4D4D4D]"
          variant="outline"
        >
          <Post />
          Post
        </Button>
      </div>
    </Sheet.Content>
  </Sheet.Root>
</nav>
