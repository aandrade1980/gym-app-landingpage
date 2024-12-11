<script>
	import CtAs from './CTAs.svelte';
	import Header from './Header.svelte';
	import SectionWrapper from './SectionWrapper.svelte';
	import Stars from './Stars.svelte';
</script>

<SectionWrapper id="hero">
	<Header />

	<div class="flex flex-1 flex-col items-center justify-center gap-10 pb-10 md:pb-14">
		<h2
			class="mx-auto w-full max-w-[1200px] text-center text-5xl font-semibold sm:text-6xl md:text-7xl lg:text-8xl"
		>
			<p>
				<span class="text-indigo-400">Gym</span> Training
				<span class="text-slate-600 line-through">Is Hard</span>
			</p>
			<p>Just Got <span class="text-indigo-400">Easier</span></p>
		</h2>
		<p
			class="mx-auto w-full max-w-[1000px] text-center text-xl sm:text-2xl md:text-3xl lg:text-4xl"
		>
			Less thinking & more doing. We're the trainer in your pocket full of <span class="italic"
				>personalized workouts, exercises, explanations, analytics
			</span> and much much more.
		</p>
		<CtAs dark={false} />
		<Stars />
	</div>
</SectionWrapper>
