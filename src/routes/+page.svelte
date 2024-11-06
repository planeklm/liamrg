<script>
	import Icon from '@iconify/svelte';
	import { fade, fly, scale } from 'svelte/transition';
	import { onMount } from 'svelte';

	let ready = false;

	onMount(() => (ready = true));
</script>

{#if ready}
	<div class="bg-white">
		<header class="absolute inset-x-0 top-0 z-50">
			<nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
				<div class="flex lg:flex-1">
					<a href="#" class="-m-r5.5 p-1.5">
						<span class="sr-only">Your Company</span>
						<p
							in:fly={{ y: -20, duration: 1000 }}
							class="text-pretty text-lg font-bold text-black sm:text-xl/8"
						>
							Liam RG
						</p>
					</a>
				</div>
				<!-- Mobile menu button remains the same -->
				<div class="hidden lg:flex lg:gap-x-12">
					<a
						href="https://youtube.com/@liamrg08/"
						in:fly={{ y: -20, duration: 1000, delay: 200 }}
						class="text-3xl font-semibold text-gray-900 transition-transform hover:scale-110"
					>
						<Icon icon="line-md:youtube-filled" />
					</a>
					<a
						href="https://www.instagram.com/liamrg08_/"
						in:fly={{ y: -20, duration: 1000, delay: 400 }}
						class="text-3xl font-semibold text-gray-900 transition-transform hover:scale-110"
					>
						<Icon icon="line-md:instagram" />
					</a>
					<a
						href="#"
						in:fly={{ y: -20, duration: 1000, delay: 600 }}
						class="text-3xl font-semibold text-gray-900 transition-transform hover:scale-110"
					>
						<Icon icon="line-md:star-filled" />
					</a>
				</div>
				<div class="hidden lg:flex lg:flex-1 lg:justify-end">
					<a
						href="#"
						in:fly={{ y: -20, duration: 1000, delay: 800 }}
						class="text-sm/6 font-semibold text-gray-900 transition-all hover:text-blue-600"
					>
						Log in <span aria-hidden="true">&rarr;</span>
					</a>
				</div>
			</nav>
			<!-- Mobile menu remains the same -->
		</header>

		<div class="relative isolate px-6 pt-15 lg:px-8">
			<!-- Background gradients remain the same -->
			<div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
				<div class="text-center">
					<div class="mb-8 flex justify-center">
						<img
							in:scale={{ duration: 1000, delay: 200 }}
							class="h-36 w-auto rounded-full object-cover shadow-lg transition-transform hover:scale-105"
							src="src/routes/liam.png"
							alt="Liam Rodgers-Gray"
						/>
					</div>
					<h1
						in:fly={{ y: 20, duration: 1000, delay: 400 }}
						class="text-balance text-5xl font-semibold tracking-tight text-gray-900 sm:text-7xl"
					>
						Liam Rodgers-Gray
					</h1>
					<p
						in:fly={{ y: 20, duration: 1000, delay: 600 }}
						class="mt-8 text-pretty text-lg font-medium text-gray-500 sm:text-xl/8"
					>
						Specialising in acting, creating and more.
					</p>
					<div
						in:fade={{ duration: 1000, delay: 800 }}
						class="mt-10 flex items-center justify-center gap-x-6"
					>
						<a
							href="#"
							class="rounded-md bg-blue-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm transition-all hover:bg-blue-500 hover:scale-105 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600"
						>
							Learn more <span aria-hidden="true">→</span>
						</a>
					</div>
				</div>
			</div>
			<!-- Bottom gradient remains the same -->
		</div>
	</div>
{/if}

<style>
	/* Optional: Add smooth transitions for all interactive elements */
	:global(*) {
		transition: all 0.2s ease-in-out;
	}
</style>
