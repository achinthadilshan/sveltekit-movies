<script>
	import { onMount } from 'svelte';
	import Logo from '~icons/tabler/movie';
	import Hamburg from '~icons/ci/hamburger-md';

	let showMenu = false;

	onMount(() => {
		let innerWidth = window.innerWidth;

		function onResize() {
			innerWidth = window.innerWidth;

			if (innerWidth < 768) {
				showMenu = false;
			} else {
				showMenu = true;
			}
		}

		onResize();

		window.addEventListener('resize', onResize);
		return () => window.removeEventListener('resize', onResize);
	});
</script>

<nav class=" fixed top-0 w-full bg-slate-900 py-2">
	<div class="container mx-auto flex items-center justify-between">
		<!-- logo section -->
		<a href="/" class="flex items-center">
			<Logo class="text-4xl text-orange-500" />
			<span class="ml-2 text-lg font-semibold text-white">Movie</span>
			<span class="block rounded bg-orange-500 p-1 text-lg font-semibold leading-none text-white"
				>Hub</span
			>
		</a>

		<!-- mobile menu button -->
		<button
			on:click={() => (showMenu = !showMenu)}
			class="absolute right-4 focus:bg-transparent md:hidden"
		>
			<Hamburg class="text-4xl text-white" />
		</button>

		<!-- menu -->
		<ul
			class="absolute right-4 top-16 flex flex-col space-y-2 rounded-lg bg-slate-900 p-4 md:relative md:right-0 md:top-0 md:flex-row md:items-center md:space-x-4 md:space-y-0 {!showMenu &&
				'hidden'}"
		>
			<li>
				<a href="/" class="font-semibold text-white hover:text-orange-400">Home</a>
			</li>
			<li>
				<a href="/" class="font-semibold text-white hover:text-orange-400">About</a>
			</li>
		</ul>
	</div>
</nav>
