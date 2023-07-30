<script>
	import Icon from '~icons/ri/search-line';
	import SearchResultsList from './SearchResultsList.svelte';
</script>

<form action="" class="w-full max-w-2xl">
	<div
		class="input-wrapper mb-4 flex w-full items-center overflow-hidden rounded-lg border-2 border-slate-300 bg-transparent text-slate-200"
	>
		<input
			type="text"
			class="w-full bg-transparent px-4 text-lg leading-[48px] text-slate-200 focus:outline-none"
			placeholder="Search"
		/>
		<button type="submit" class="h-[48px] bg-transparent pr-3">
			<Icon class="text-xl text-inherit" />
		</button>
	</div>
	<SearchResultsList />
</form>

<style>
	.input-wrapper:has(input:focus) {
		border: 2px solid #f97316;
		color: #f97316;
	}
</style>
