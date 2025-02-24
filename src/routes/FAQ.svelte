<script lang="ts">
	interface FAQItem {
		question: string;
		answer: string;
		link?: string;
		isOpen: boolean;
	}

	const items: FAQItem[] = [
		{
			question: 'Was wünscht Ihr Euch?',
			answer: 'Du findest unsere Geschenkliste auf der Website unter "Geschenke".',
			link: '/geschenke',
			isOpen: false
		},
		{
			question: 'Wo kann ich parken?',
			answer: 'Du kannst bei der MABO-Bauelemente GmbH parken.',
			link: 'https://maps.app.goo.gl/iA5zHcYNNgdam1Nw8',
			isOpen: false
		},
		{
			question: 'Wie komme ich da hoch?',
			answer: 'Es ist ein schöner kurzer Spaziergang.',
			isOpen: false
		},
		{
			question: 'Wie komme ich wieder runter?',
			answer: 'Wir haben einen Shuttle-Service, der Dich abends hinunterbringt.',
			isOpen: false
		},
		{
			question: 'Wie lange dauert es?',
			answer: 'Die Veranstaltung ist open-end. Bleib so lange Du Lust und Spass hast.',
			isOpen: false
		},
		{
			question: 'Kann mein Hund mitkommen?',
			answer: 'Ja. Rika wird auch da sein, aber es gibt genug Platz.',
			isOpen: false
		}
	];

	function toggle(index: number) {
		items[index].isOpen = !items[index].isOpen;
	}
</script>

<div class="mb-24 p-6 text-center text-2xl md:text-3xl">
	<h2 class="mb-10 text-4xl md:text-7xl">Häufige Fragen</h2>
	<div class="mb-2 overflow-hidden">
		{#each items as item, i (item.question)}
			<button
				class="mt-4 flex w-full cursor-pointer items-center justify-between rounded border border-gray-300 bg-white p-4 hover:bg-gray-100"
				onclick={() => {
					toggle(i);
				}}
			>
				<span>{item.question}</span>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class={`h-5 w-5 transition-transform duration-300 ${item.isOpen ? 'rotate-180 transform' : ''}`}
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M19 9l-7 7-7-7"
					/>
				</svg>
			</button>
			<div
				class="transition-max-height overflow-hidden px-4 duration-300 {item.isOpen
					? 'max-h-screen'
					: 'max-h-0'}"
			>
				<p class="my-6">{item.answer}</p>
				{#if item.link}
					<a
						class="text-bold mb-6 block text-green-600"
						href={item.link}
						target={item.link.includes('http') ? '_blank' : '_self'}>→ Link</a
					>
				{/if}
			</div>
		{/each}
	</div>
</div>
