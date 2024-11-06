<script>
	import Icon from "@iconify/svelte";
	import { fade, fly, scale, slide } from "svelte/transition";
	import { onMount } from "svelte";

	let ready = false;
	let isMenuOpen = false;

	let starNow = "https://starnow.com/u/liamrodgersgray/";
	let youtube = "https://youtube.com/@liamrg08/";
	let instagram = "https://instagram.com/liamrg08_/";

	onMount(() => (ready = true));

	const toggleMenu = () => {
		isMenuOpen = !isMenuOpen;
	};
</script>

{#if ready}
	<div class="bg-white">
		<header class="absolute inset-x-0 top-0 z-50">
			<nav
				class="flex items-center justify-between p-6 lg:px-8"
				aria-label="Global"
			>
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
				<div class="flex lg:hidden">
					<button
						type="button"
						on:click={toggleMenu}
						class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
					>
						<span class="sr-only">Open main menu</span>
						<svg
							class="h-6 w-6"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
							/>
						</svg>
					</button>
				</div>
				<div class="hidden lg:flex lg:gap-x-12">
					<a
						href={youtube}
						in:fly={{ y: -20, duration: 1000, delay: 200 }}
						class="text-3xl font-semibold text-gray-900 transition-transform hover:scale-110"
					>
						<Icon icon="line-md:youtube-filled" />
					</a>
					<a
						href={instagram}
						in:fly={{ y: -20, duration: 1000, delay: 400 }}
						class="text-3xl font-semibold text-gray-900 transition-transform hover:scale-110"
					>
						<Icon icon="line-md:instagram" />
					</a>
					<a
						href={starNow}
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

			<!-- Mobile menu -->
			{#if isMenuOpen}
				<div
					class="lg:hidden"
					role="dialog"
					aria-modal="true"
					transition:slide
				>
					<div
						class="fixed inset-0 z-50 bg-black bg-opacity-25"
						on:click={toggleMenu}
					></div>
					<div
						class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
					>
						<div class="flex items-center justify-between">
							<a href="#" class="-m-1.5 p-1.5">
								<span class="sr-only">Your Company</span>
								<p class="text-lg font-bold">Liam RG</p>
							</a>
							<button
								type="button"
								class="-m-2.5 rounded-md p-2.5 text-gray-700"
								on:click={toggleMenu}
							>
								<span class="sr-only">Close menu</span>
								<svg
									class="h-6 w-6"
									fill="none"
									viewBox="0 0 24 24"
									stroke-width="1.5"
									stroke="currentColor"
									aria-hidden="true"
								>
									<path
										stroke-linecap="round"
										stroke-linejoin="round"
										d="M6 18L18 6M6 6l12 12"
									/>
								</svg>
							</button>
						</div>
						<div class="mt-6 flow-root">
							<div class="-my-6 divide-y divide-gray-500/10">
								<div class="space-y-2 py-6">
									<a
										href={youtube}
										class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
									>
										<div class="flex items-center gap-2">
											<Icon
												icon="line-md:youtube-filled"
											/>
											YouTube
										</div>
									</a>
									<a
										href={instagram}
										class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
									>
										<div class="flex items-center gap-2">
											<Icon icon="line-md:instagram" />
											Instagram
										</div>
									</a>
									<a
										href={starNow}
										class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
									>
										<div class="flex items-center gap-2">
											<Icon icon="line-md:star-filled" />
											StarNow
										</div>
									</a>
								</div>
								<div class="py-6">
									<a
										href="#"
										class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
									>
										Log in
									</a>
								</div>
							</div>
						</div>
					</div>
				</div>
			{/if}
		</header>

		<div class="relative isolate px-6 pt-15 lg:px-8">
			<div
				class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
				aria-hidden="true"
			>
				<div
					class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#3662e3] to-[#3662e3] opacity-30 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
					style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
				></div>
			</div>
			<div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
				<div class="text-center">
					<div class="mb-8 flex justify-center">
						<img
							in:scale={{ duration: 1000, delay: 200 }}
							class="h-36 w-auto rounded-full object-cover shadow-lg transition-transform hover:scale-105"
							src="https://files.catbox.moe/r6f4y3.png"
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
			<div
				class="absolute inset-x-0 top-[calc(100%-13rem)] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[calc(100%-30rem)]"
				aria-hidden="true"
			>
				<div
					class="relative left-[calc(50%+3rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 bg-gradient-to-tr from-[#3662e3] to-[#3662e3] opacity-30 sm:left-[calc(50%+36rem)] sm:w-[72.1875rem]"
					style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
				></div>
			</div>
		</div>
	</div>
{/if}

<style>
	:global(*) {
		transition: all 0.2s ease-in-out;
	}
</style>
