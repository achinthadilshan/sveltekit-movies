<script>
	import Icon from '~icons/ri/search-line';
</script>

<form action="" class="w-full max-w-2xl">
	<div class="flex input-wrapper items-center text-slate-200 w-full bg-transparent overflow-hidden rounded-lg border-2 border-slate-300">
		<input type="text" class="bg-transparent w-full focus:outline-none leading-[48px] px-4 text-lg text-slate-200" placeholder="Search" />
        <button type="submit" class="h-[48px] pr-3 bg-transparent">
            <Icon class="text-xl text-inherit"/>
        </button>
	</div>
</form>

<style>
    .input-wrapper:has(input:focus) {
        border: 2px solid #f97316;
        color: #f97316;
    }
</style>
