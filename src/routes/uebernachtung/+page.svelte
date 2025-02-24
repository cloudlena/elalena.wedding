<script lang="ts">
	import type { LatLngExpression } from 'leaflet';
	import Map from '$lib/Map.svelte';
	import rebstock from './rebstock.jpg';
	import schusterjunge from './schusterjunge.avif';
	import linde from './linde.jpg';
	import waldulm from './rebstock-waldulm.jpg';
	import faxe from './faxe.jpg';
	import williams from './williams.jpg';
	import prinzen from './prinzen.jpg';
	import perle from './perle.jpg';
	import muehlenhof from './muehlenhof.jpg';
	import spinner from './spinner.jpg';
	import mighty2 from './mighty2.jpg';
	import graessel from './graessel.avif';
	import sonne from './sonne.jpg';
	import jaeger from './jaeger.webp';
	import leben from './leben.jpeg';
	import heimat from './heimat.jpg';
	import baeuerlehof from './baeuerlehof.jpg';

	interface Stay {
		name: string;
		image: string;
		link: string;
		googleMapsID: string;
		coordinates: LatLngExpression;
		distanceMinutes: number;
		rating: number;
		ratingCount: number;
	}

	const stays: Stay[] = [
		{
			name: 'Jägerhof',
			image: jaeger,
			link: 'https://benzottenhoefen.wixsite.com/jaegerhof-benz',
			googleMapsID: 'v2aHUURLh658xazQ6',
			coordinates: [48.5834689, 8.1460541],

			distanceMinutes: 1,
			rating: 4.8,
			ratingCount: 29
		},
		{
			name: 'Landgasthof Rebstock',
			image: rebstock,
			link: 'https://www.landgasthofrebstock.de/',
			googleMapsID: 'm8kpTmd6yWntdSsc9',
			coordinates: [48.5795887, 8.1330446],
			distanceMinutes: 3,
			rating: 4.4,
			ratingCount: 1061
		},
		{
			name: 'Pension Heimat',
			image: heimat,
			link: 'http://www.pension-heimat.de/',
			googleMapsID: 'CegAd9NEaPp6est66',
			coordinates: [48.5711844, 8.1417912],
			distanceMinutes: 5,
			rating: 4.8,
			ratingCount: 66
		},
		{
			name: 'Pension Mühlenhof',
			image: muehlenhof,
			link: 'https://www.pension-muehlenhof.de/',
			googleMapsID: 'b8XvuxageaPRwS197',
			coordinates: [48.5682535, 8.1359451],
			distanceMinutes: 6,
			rating: 4.8,
			ratingCount: 26
		},
		{
			name: 'Zum Prinzen',
			image: prinzen,
			link: 'http://www.zumprinzen.de/',
			googleMapsID: '2uJcTZkKjeYFSXFPA',
			coordinates: [48.5906497, 8.1153226],
			distanceMinutes: 6,
			rating: 4.2,
			ratingCount: 223
		},
		{
			name: 'Gasthaus Linde Oberachern',
			image: linde,
			link: 'http://www.lindeoberachern.de/',
			googleMapsID: 'qZxQegVziiiTxXKg7',
			coordinates: [48.6162396, 8.081512],
			distanceMinutes: 9,
			rating: 4.5,
			ratingCount: 226
		},
		{
			name: 'Hotel "Faxe" Schwarzwälder Hof',
			image: faxe,
			link: 'http://www.faxehof.de/',
			googleMapsID: '6i5w2FHkAqSY5Ray6',
			coordinates: [48.5850432, 8.1004391],
			distanceMinutes: 9,
			rating: 4.4,
			ratingCount: 380
		},
		{
			name: 'mightyTwice Hotel Achern',
			image: mighty2,
			link: 'https://www.twicehotels.de/achern',
			googleMapsID: '75PEatRCa7edag4T6',
			coordinates: [48.6253106, 8.0780627],
			distanceMinutes: 10,
			rating: 4.6,
			ratingCount: 203
		},
		{
			name: 'Rebstock Waldulm Hotel & Restaurant',
			image: waldulm,
			link: 'https://rebstock-waldulm.de/',
			googleMapsID: 'CBQkVyZ8azuViXhU6',
			coordinates: [48.5816702, 8.1024251],
			distanceMinutes: 10,
			rating: 4.5,
			ratingCount: 404
		},
		{
			name: 'Pension Williams',
			image: williams,
			link: 'http://www.pension-williams.com/contact_us.html',
			googleMapsID: 'xPAvq5UgVcKjNh9Y9',
			coordinates: [48.5797902, 8.1768849],
			distanceMinutes: 11,
			rating: 4.7,
			ratingCount: 170
		},
		{
			name: 'Gasthaus zur Grässelmühle',
			image: graessel,
			link: 'http://www.graesselmuehle.de/',
			googleMapsID: 'JJdMmosh8CNh7pn7A',
			coordinates: [48.6246516, 8.1018583],
			distanceMinutes: 11,
			rating: 4.4,
			ratingCount: 346
		},
		{
			name: 'Schusterjunge Aparthotel Sasbachwalden',
			image: schusterjunge,
			link: 'https://www.schusterjunge-aparthotel.de/',
			googleMapsID: '3ZbFbjFJxujkv5bz9',
			coordinates: [48.6183827, 8.1224028],
			distanceMinutes: 12,
			rating: 5,
			ratingCount: 43
		},
		{
			name: 'Ferienwohnung Schwarzwaldleben',
			image: leben,
			link: 'https://www.schwarzwaldleben.com/',
			googleMapsID: 'XM34vnsKrkr82i7A7',
			coordinates: [48.5810177, 8.1773364],
			distanceMinutes: 12,
			rating: 5,
			ratingCount: 1
		},
		{
			name: 'Sonne Eintracht',
			image: sonne,
			link: 'http://www.hotel-sonne-eintracht.com/',
			googleMapsID: 'D2dHeuKxLLv6HgCeA',
			coordinates: [48.6290961, 8.0745853],
			distanceMinutes: 12,
			rating: 4.3,
			ratingCount: 535
		},
		{
			name: 'Bäuerlehof',
			image: baeuerlehof,
			link: 'http://www.baeuerlehof.de/',
			googleMapsID: 'TErz886F5tGc9UwL7',
			coordinates: [48.5792004, 8.1886692],
			distanceMinutes: 13,
			rating: 4.7,
			ratingCount: 110
		},
		{
			name: 'Hotel Restaurant Spinnerhof',
			image: spinner,
			link: 'http://spinnerhof.de/',
			googleMapsID: 'rZmoXkwLo6FUWywk9',
			coordinates: [48.6151052, 8.140559],
			distanceMinutes: 15,
			rating: 4.6,
			ratingCount: 1299
		},
		{
			name: 'Schwarzwaldperle',
			image: perle,
			link: 'http://hotel-schwarzwaldperle.de/',
			googleMapsID: '9L6daQNQMS1tbrCMA',
			coordinates: [48.6140251, 8.1614526],
			distanceMinutes: 18,
			rating: 4.7,
			ratingCount: 394
		}
	];
</script>

<div class="mx-auto max-w-4xl">
	<div class="mt-12 mb-24 text-center">
		<h1 class="mb-4 text-4xl md:text-6xl">Übernachtungsmöglichkeiten</h1>
		<p class="text-3xl md:text-5xl">in der Umgebung</p>
	</div>

	<div class="mb-16 h-80 px-6 md:h-[648px]">
		<Map markers={stays} />
	</div>

	<div class="mb-24 grid gap-6 p-6 text-center text-3xl md:grid-cols-3 md:text-5xl">
		{#each stays as stay (stay.name)}
			<div class="max-w-sm overflow-hidden rounded bg-white shadow-lg">
				<img class="mb-6 h-50 w-full object-cover" src={stay.image} alt={stay.name} />
				<div class="px-6">
					<div class="mb-4 min-h-18 text-2xl font-bold">{stay.name}</div>
					<p class="mb-4 text-base text-xl text-gray-700">
						<strong>↱ {stay.distanceMinutes} min</strong><br />
						{stay.rating}
						{'★'.repeat(Math.floor(stay.rating))}{'✭'.repeat(
							Math.round(stay.rating - Math.floor(stay.rating))
						)}{'☆'.repeat(5 - Math.round(stay.rating))}({stay.ratingCount})
					</p>
				</div>
				<div class="flex px-6 py-2">
					<a
						class="mr-2 mb-2 inline-block w-full rounded-full bg-green-900 px-3 py-1 text-sm font-semibold text-white hover:bg-green-700"
						href={stay.link}
						target="_blank"
						rel="noopener noreferrer">Website</a
					>
					<a
						class="mr-2 mb-2 inline-block w-full rounded-full bg-green-900 px-3 py-1 text-sm font-semibold text-white hover:bg-green-700"
						href="https://maps.app.goo.gl/{stay.googleMapsID}"
						target="_blank"
						rel="noopener noreferrer">Google Maps</a
					>
				</div>
			</div>
		{/each}
	</div>
</div>
