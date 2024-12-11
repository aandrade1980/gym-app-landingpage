<script>
	import { openModal } from '../state.svelte';

	const aClass = 'cursor-pointer duration-200 hover:text-indigo-400';
</script>

<header class="relative z-20 flex flex-col">
	<div class="mx-auto flex w-full max-w-[1400px] items-center justify-between px-4 py-6">
		<a href="/">
			<h1 class="font-semibold">Swoley <span class="text-indigo-400">Moley</span></h1>
		</a>
		<button
			type="button"
			onclick={() => (openModal.value = !openModal.value)}
			class="grid place-items-center md:hidden"
			aria-label="Toggle menu"
		>
			<i class="fa-solid fa-bars"></i>
		</button>
		<nav class="hidden items-center gap-4 md:flex lg:gap-6">
			<a href="#product" class={aClass}>Product</a>
			<a href="#reviews" class={aClass}>Reviews</a>
			<a href="#faqs" class={aClass}>FAQs</a>
			<button class="specialBtn" type="button">
				<p>Start free today</p>
			</button>
		</nav>
	</div>
</header>
