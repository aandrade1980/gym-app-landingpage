<script>
	const { id, children } = $props();
</script>

<section {id} class={'flex min-h-screen flex-col px-4'}>
	<div class="mx-auto flex w-full max-w-[1400px] flex-1 flex-col">
		{@render children()}
	</div>
</section>
