<script lang="ts">
	let showMenu = $state(false);

	interface Entry {
		label: string;
		link: string;
		newTab?: boolean;
	}

	const entries: Entry[] = [
		{ label: 'Home', link: '/' },
		{ label: 'Übernachtungen', link: '/uebernachtung' },
		{ label: 'Bilder', link: 'https://drive.proton.me/urls/JAGS81P848#uEJB1UxamSty', newTab: true },
		{ label: 'Geschenke', link: '/geschenke' }
	];

	function toggleMenu() {
		showMenu = !showMenu;
	}
</script>

{#if showMenu}
	<div
		class="fixed top-0 left-0 w-full bg-amber-100 text-center text-3xl opacity-95 shadow-md"
		style="z-index:9998"
	>
		<ul class="my-8">
			{#each entries as entry (entry.label)}
				<li class="py-4">
					<a
						class="hover:text-green-600"
						onclick={toggleMenu}
						href={entry.link}
						target={entry.newTab ? '_blank' : '_self'}
						rel="noopener noreferrer">{entry.label}</a
					>
				</li>
			{/each}
		</ul>
	</div>
{/if}

<button class="cursor-pointer" onclick={toggleMenu}>
	<div
		class="text-middle fixed top-2 right-2 flex h-12 w-12 items-center justify-center rounded-full bg-white opacity-50 shadow-md hover:opacity-100 md:top-4 md:right-4"
		style="z-index:9999"
	>
		<svg
			width="28px"
			height="28px"
			viewBox="0 0 24 24"
			fill="none"
			xmlns="http://www.w3.org/2000/svg"
		>
			{#if showMenu}
				<path d="M4 20L20 4" stroke="#14532D" stroke-width="2" stroke-linecap="round" />
				<path d="M4 4L20 20" stroke="#14532D" stroke-width="2" stroke-linecap="round" />
			{:else}
				<path d="M4 18L20 18" stroke="#14532D" stroke-width="2" stroke-linecap="round" />
				<path d="M4 12L20 12" stroke="#14532D" stroke-width="2" stroke-linecap="round" />
				<path d="M4 6L20 6" stroke="#14532D" stroke-width="2" stroke-linecap="round" />
			{/if}
		</svg>
	</div>
</button>
