<script lang="ts">
	import '../app.css';
	import CtAs from '../components/CTAs.svelte';
	import Footer from '../components/Footer.svelte';
	import Header from '../components/Header.svelte';

	import { openModal } from '../state.svelte';

	const { children } = $props();

	let y = $state() as number;
	let outerHeight = $state(0);

	function reroute(href: string) {
		openModal.value = false;
		window.location.href = href;
	}
</script>

{#if openModal.value}
	<div
		class="fixed left-0 top-0 z-50 flex h-screen w-screen flex-col gap-8 border-b bg-white p-5 px-8 md:hidden"
	>
		<div class="flex items-center justify-between gap-4 border-b pb-2">
			<h1 class="font-semibold">
				Swoley <span class="text-indigo-400">Moley</span>
			</h1>
			<button
				onclick={() => (openModal.value = false)}
				class="border-none outline-none"
				aria-label="close"
			>
				<i class="fa-solid fa-xmark text-2xl"></i>
			</button>
		</div>
		<div class="flex flex-1 flex-col gap-4">
			<button
				onclick={() => reroute('#product')}
				class="group cursor-pointer border-none p-2 text-left outline-none duration-200"
			>
				<p class="poppins text-3xl font-semibold duration-200 group-hover:pl-2">
					Product <i class="fa-solid fa-chevron-right pl-4 text-xl"></i>
				</p>
			</button>
			<button
				onclick={() => reroute('#reviews')}
				class="group cursor-pointer border-none p-2 text-left outline-none duration-200"
			>
				<p class="poppins text-3xl font-semibold duration-200 group-hover:pl-2">
					Reviews <i class="fa-solid fa-chevron-right pl-4 text-xl"></i>
				</p>
			</button>
			<button
				onclick={() => reroute('#faqs')}
				class="group cursor-pointer border-none p-2 text-left outline-none duration-200"
			>
				<p class="poppins text-3xl font-semibold duration-200 group-hover:pl-2">
					FAQs <i class="fa-solid fa-chevron-right pl-4 text-xl"></i>
				</p>
			</button>
		</div>
		<div class="flex flex-col items-center justify-center">
			<CtAs dark={false} />
		</div>
	</div>
{/if}

{#if y > outerHeight}
	<div class="fadeIn fixed left-0 top-0 z-20 flex w-full flex-col bg-white px-4">
		<Header />
	</div>
{/if}

{@render children()}

<Footer />

<svelte:window bind:scrollY={y} bind:outerHeight />
