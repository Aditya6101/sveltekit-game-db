<script context="module">
	export async function load({ params: { id } }) {
		const API_KEY = import.meta.env.VITE_API_KEY;
		const url = `https://api.rawg.io/api/games/${id}?key=${API_KEY}`;
		const res = await fetch(url);
		const data = await res.json();
		return {
			props: { data }
		};
	}
</script>

<script>
	import { fade } from 'svelte/transition';

	export let data;

	// @ts-ignore
	let ratingBg = data.rating >= 4 ? 'bg-green-600' : 'bg-red-600';
</script>

<svelte:head>
	<title>{data.name} | GameDB by Aditya Kamble</title>
</svelte:head>

<main class="max-w-5xl mx-auto px-6 my-6" transition:fade={{ delay: 250, duration: 300 }}>
	<img class="rounded-md" src={data.background_image} alt={data.name} />
	<div class="my-4 flex items-center justify-between">
		<h2 class="font-bold text-xl">{data.name}</h2>
		<span class={`px-2 py-1 font-bold text-base text-white ${ratingBg} rounded-md `}
			>{data.rating}</span
		>
	</div>
	<p class="mb-4 font-normal text-base text-gray-800 leading-7">{data.description_raw}</p>
	<a href={data.website} class="font-bold text-lg text-blue-800"> Visit Official Website</a>
</main>
