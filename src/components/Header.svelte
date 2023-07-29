<script>
	import SearchForm from './SearchForm.svelte';
</script>

<div class="banner h-screen w-full bg-cover">
	<div class="container mx-auto flex h-full flex-col items-center justify-center">
		<div>
			<h1 class="text-center text-3xl font-bold uppercase tracking-widest text-slate-200">
				Unlimited Movies
			</h1>
			<p class="text-slate-200">Watch anywhere you go</p>
		</div>
		<SearchForm />
	</div>
</div>

<style>
	.banner {
		background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
			url('/images/banner.jpg');
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
	}
</style>
