<script lang="ts">
	import "../app.postcss";
	import { Toaster } from "svelte-sonner";
	import { page } from "$app/stores";
	import Navbar from "$lib/components/layout/Navbar.svelte";

	let { children } = $props();
</script>

<svelte:head>
	<title>{$page.data.title} - KOKOA</title>
	<meta name="description" content={$page.data.description} />
</svelte:head>

<Navbar />
{@render children()}
<Toaster richColors closeButton />
