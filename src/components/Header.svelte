<script>
	import SearchForm from './SearchForm.svelte';
</script>

<div class="banner h-screen w-full bg-cover">
	<div class="container mx-auto flex h-full flex-col items-center justify-center">
		<div class="text-center mb-10 md:mb-16 text-white">
			<h1 class="text-center text-4xl md:text-5xl mb-2 font-bold uppercase tracking-widest">
				Unlimited Movies
			</h1>
			<p class="text-lg md:text-xl font-light">Watch anywhere you go.</p>
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
