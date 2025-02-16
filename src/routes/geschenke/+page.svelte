<script lang="ts">
	import japan from '$lib/images/japan.jpeg';
	import gardenBed from '$lib/images/garden-bed.jpeg';
	import towels from '$lib/images/towels.jpeg';
	import ebike from '$lib/images/ebike.jpeg';
	import treats from '$lib/images/treats.jpeg';
	import solderingIron from '$lib/images/soldering-iron.jpeg';
	import bed from '$lib/images/bed.jpeg';
	import overlockMachine from '$lib/images/overlock-machine.jpeg';
	import standingDesk from '$lib/images/standing-desk.jpeg';

	interface Gift {
		name: string;
		description: string;
		image: string;
	}

	const gifts: Gift[] = [
		{
			name: 'Reise nach Japan',
			description: 'Wir planen schon länger eine Reise nach Japan',
			image: japan
		},
		{
			name: 'Overlock-Nähmaschine für Ela',
			description: 'Elas Overlock ist in die Jahre gekommen. Ein Update wäre schön.',
			image: overlockMachine
		},
		{
			name: 'Lastenrad für Lena',
			description: 'Lena ist gerne mit dem Velo unterwegs und möchte mehr transportieren können',
			image: ebike
		},
		{
			name: 'Knuspies für Rika',
			description: 'Die kleine Maus freut sich sehr über Gourmet-Leckerchen',
			image: treats
		},
		{
			name: 'Neue Handtücher',
			description: 'Wir benutzen schon lange dieselben Handtücher',
			image: towels
		},
		{
			name: 'Hochbeet für Ela',
			description: 'Wir haben nur beschränkt Platz, aber Ela möchte gärtnern',
			image: gardenBed
		},
		{
			name: 'Lötkolben für Lena',
			description: 'Lena bastelt gerne mit Elektronikteilen, z.B. für den Home Assistant',
			image: solderingIron
		},
		{
			name: 'Neues Bettchen für Rika',
			description: 'Nach vier Jahren ist Rikas Bettchen etwas durch',
			image: bed
		},
		{
			name: 'Verstellbare Schreibtische',
			description: 'Wir möchten im Home-Office ergonomischer arbeiten',
			image: standingDesk
		}
	];
</script>

<div class="mx-auto max-w-4xl">
	<div class="mt-12 mb-24 px-4 text-center">
		<h1 class="mb-4 text-4xl md:text-6xl">Geschenke</h1>
		<p class="text-2xl md:text-4xl">
			Diese Sachen wünschen wir uns schon lange. Gerne könnt ihr uns einen Anteil daran schenken.
		</p>
	</div>

	<div class="mb-24 grid gap-6 p-6 text-center text-3xl md:grid-cols-3 md:text-5xl">
		{#each gifts as gift}
			<div class="max-w-sm overflow-hidden rounded bg-white shadow-lg">
				<img class="mb-6 h-54 w-full object-cover" src={gift.image} alt={gift.name} />
				<div class="px-6">
					<div class="mb-4 min-h-14 text-2xl font-bold">{gift.name}</div>
					<p class="mb-4 min-h-24 text-base text-xl text-gray-700">{gift.description}</p>
				</div>
				<div class="flex px-6 pb-2">
					<a
						class="mr-2 mb-2 inline-block w-full rounded-full bg-green-900 px-3 py-1 text-sm font-semibold text-white hover:bg-green-700"
						href="/danke?gift={gift.name}"
						target="_blank"
						rel="noopener noreferrer">Anteil Schenken</a
					>
				</div>
			</div>
		{/each}
	</div>
</div>
