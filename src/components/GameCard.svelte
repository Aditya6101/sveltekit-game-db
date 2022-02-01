<script>
	import { slide } from 'svelte/transition';
	export let game;
</script>

<div class="w-36" in:slide={{ delay: 250, duration: 500 }}>
	<a href={`/games/${game.id}`}>
		<img
			class="w-full h-52 object-cover rounded-md overflow-hidden  transition ease-in  hover:scale-105"
			src={game.background_image}
			alt={game.name}
		/>
	</a>
	<h3 class="mt-2 mb-1 text-base font-bold text-gray-900 truncate">
		{game.name}
	</h3>
	<p class="text-sm font-medium text-stone-500">
		{game.released}
	</p>
</div>
