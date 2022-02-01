<script context="module">
	export async function load({ params: { page_number } }) {
		const API_KEY = import.meta.env.VITE_API_KEY;
		const url = `https://api.rawg.io/api/games?key=${API_KEY}&page=${page_number}&page_size=20`;
		const res = await fetch(url);
		const data = await res.json();
		return {
			// @ts-ignore
			props: { data: data.results, currentPageNumber: +page_number, totalCount: data.count }
		};
	}
</script>

<script>
	import GameCard from '../../components/GameCard.svelte';
	import Pagination from '../../components/Pagination.svelte';
	export let data;
	export let currentPageNumber;
	export let totalCount;
</script>

<svelte:head>
	<title>Explore Games | GameDB by Aditya Kamble</title>
</svelte:head>

<div class="max-w-5xl mx-auto py-3 px-6 grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5  gap-11">
	{#each data as game (game.id)}
		<GameCard {game} />
	{/each}
</div>

<Pagination {totalCount} {currentPageNumber} />
