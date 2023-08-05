<script>
	export let movies;
</script>

<div class="top absolute left-0 top-16 w-full rounded-lg bg-white/80 px-2 py-4">
	<ul class="mr-4 max-h-[25vh] w-full overflow-y-auto">
		{#if movies.length > 0}
			{#each movies as movie}
				<li class=" border-b border-slate-200">
					<a href="/" target="_blank" class="flex items-center space-x-4 py-2">
						<img
							src={`https://image.tmdb.org/t/p/w500/${movie.poster_path}`}
							class="h-16 w-12 object-cover"
							alt="movie thumbnail"
						/>
						<span class="font-semibold text-slate-700">{movie.title}</span>
					</a>
				</li>
			{/each}
		{:else}
			<li>
				<span class="font-semibold text-slate-700">No results found</span>
			</li>
		{/if}
	</ul>
</div>

<style>
	ul {
		scrollbar-gutter: stable both-edges;
	}
</style>
