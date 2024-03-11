<script>
    import DuggupLogo from "$lib/icons/DuggupLogo.svelte";
    import Home from "$lib/icons/Home.svelte";
    import Explore from "$lib/icons/Explore.svelte";
    import Learn from "$lib/icons/Learn.svelte";
    import Post from "$lib/icons/Post.svelte";
    import Button from "./ui/button/button.svelte";
     import {ChevronDown} from "lucide-svelte";
    import * as Avatar from "$lib/components/ui/avatar/index.js";
    import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
</script>

<nav class="py-5 flex items-center justify-between border-b-[0.5px] border-[#525C69] border-dotted">
    <div class="flex gap-x-1">
        <DuggupLogo />
        <p class="text-xl font-bold text-[#333333]">duggup</p>
    </div>
    <div class="flex gap-x-10">
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
        <Button class="gap-x-2 text-[#4D4D4D] font-normal px-6 py-0 border-[0.5px] border-[#4D4D4D] custom-shadow rounded-[4px]" variant="outline">
            <Post />
            Post
        </Button>
        <div class="flex">
            <Avatar.Root class="border-[0.5px] border-[#4D4D4D]">
  <Avatar.Image src="images/krishnaKiran.png" alt="@shadcn" />
  <Avatar.Fallback>CN</Avatar.Fallback>
</Avatar.Root>
            <DropdownMenu.Root>
                <DropdownMenu.Trigger asChild let:builder>
                 <Button variant="ghost" class="text-[20px] font-medium text-[#4D4D4D] gap-x-3" builders={[builder]}>Krishna Kiran <ChevronDown class="" /></Button>
                 </DropdownMenu.Trigger>
                    <DropdownMenu.Content class="w-56">
   
    
                    </DropdownMenu.Content>
                </DropdownMenu.Root>
        </div>
    </div>
</nav>