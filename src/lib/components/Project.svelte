<script lang="ts">
	import Tag from "$lib/components/Tag.svelte";

	type Author = {
		name: string;
		url_image: string;
	};

	type Props = {
		id: number;
		term: string;
		name: string;
		categories: string[];
		description: string;
		authors: Author[];
	};

	let { id, term, name, categories, description /* authors  */ }: Props = $props();
</script>

<!-- TODO: Use semantic CSS https://www.magentaa11y.com/checklist-web/link/#complex-examples -->
<div class="m-4 max-w-72 rounded-2xl bg-neutral-800 px-6 py-4">
	<div class="mb-4">
		<span class="font-fira font-medium text-lime-500">{term}</span>
		<h2 class="font-fira text-xl font-medium text-white">{name}</h2>
	</div>
	<div class="flex flex-wrap gap-1">
		{#each categories as category}
			<Tag {category} />
		{/each}
	</div>
	<p class="my-4">{description}</p>
	<div class="flex w-full flex-row justify-between">
		<div class="flex flex-row items-center justify-center">
			<!-- TODO: Implement author's avatars -->
			<!-- {#each authors as author}
				<img src="https://via.placeholder.com/150" alt={author} class="h-4 w-4 rounded-full" />
			{/each} -->
		</div>
		<a href="/projects/{id}">
			<button class="rounded-full bg-lime-500 px-2 font-fira text-sm font-bold text-black">
				Ver más
			</button>
		</a>
	</div>
</div>
