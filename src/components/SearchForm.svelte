<script>
	import Icon from '~icons/ri/search-line';
	import Loading from '~icons/line-md/loading-alt-loop';
	import SearchResultsList from './SearchResultsList.svelte';

	let search = '';
	let movies = [];
	let timeout;
	let loading = false;

	function handle_search() {
		loading = true;
		if (timeout) clearTimeout(timeout);
		timeout = setTimeout(search_movies, 500);
	}

	async function search_movies() {
		if (!search) {
			reset();
			return;
		}

		try {
			const options = {
				method: 'GET',
				headers: {
					accept: 'application/json',
					Authorization:
						'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJmOWM0YWVkOTRjZTZkYmNlZmM5MjMxNGNiMDQ0ZjJhNiIsInN1YiI6IjY0YmU4YzkzNThlZmQzMDBmZjFjNWI3ZiIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.TTpQR13CiMqKlsgXzMT37UKpleotexOfj8NzNYQ_2nA'
				}
			};

			const res = await fetch(`https://api.themoviedb.org/3/search/movie?query=${search}`, options);
			const data = await res.json();
			movies = data?.results || [];
			loading = false;
		} catch (e) {
			console.log(e);
			reset();
		}
	}

	function handleError() {
		alert('Something went wrong.');
		reset();
	}

	function reset() {
		movies = [];
		loading = false;
	}
</script>

<div class="relative w-full max-w-2xl">
	<div
		class="input-wrapper flex w-full items-center overflow-hidden rounded-lg border-2 border-slate-300 bg-transparent text-slate-200"
	>
		<input
			type="text"
			class="w-full bg-transparent px-4 text-lg leading-[48px] text-slate-200 focus:outline-none"
			placeholder="Search"
			bind:value={search}
			on:input={handle_search}
		/>
		{#if loading}
			<Loading class="mx-3 text-2xl text-inherit" />
		{:else}
			<Icon class="mx-3 text-xl text-inherit" />
		{/if}
	</div>
	<SearchResultsList {movies} />
</div>

<style>
	.input-wrapper:has(input:focus) {
		border: 2px solid #f97316;
		color: #f97316;
	}
</style>
