<script>
  import "../app.pcss";
  import Navbar from "$lib/components/Navigation/Navbar.svelte";
  import MobileNav from "$lib/components/Navigation/MobileNav.svelte";
</script>

<Navbar />
<MobileNav />
<slot />
