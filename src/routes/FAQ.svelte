<script lang="ts">
	interface FAQItem {
		question: string;
		answer: string;
		link?: string;
		isOpen: boolean;
	}

	const items: FAQItem[] = [
		{
			question: 'Wie reise ich mit den öffentlichen Verkehrsmitteln an?',
			answer:
				'Die nächste Haltestelle ist "Bahnhof Furschenbach". Von da geht ihr ca. 20 min auf einer geteerten Strasse den Berg hoch zur Location. Du würdest abends gerne länger bleiben, weisst aber noch nicht, wie Du wieder ins Hotel zurückkommst? Melde Dich bitte frühzeitig bei uns, damit wir einen Shuttle-Dienst organisieren können.',
			link: 'https://www.bwegt.de/fahrplanauskunft/trip?formik=destination%3Dde%253A08317%253A13753%26itdDateDayMonthYear%3D20092025%26itdTime%3D1040%26itdTripDateTimeDepArr%3Darr%26origin%3Dde%253A08317%253A33013&lng=de&trip=multiModalitySelected%3Dpt',
			isOpen: false
		},
		{
			question: 'Wie reise ich mit dem Auto an?',
			answer:
				'Du kannst direkt mit dem Auto zur Location fahren. Beim Lebenshof gibt es genügend Parkplätze. Die Adresse ist "Am Bach 17 in 77883 Ottenhöfen".',
			link: 'https://maps.app.goo.gl/rtY99UwVGsZbJRHF9',
			isOpen: false
		},
		{
			question: 'Hat jemand noch Platz im Auto? Kann ich noch wen mitnehmen?',
			answer:
				'Es gibt eine Signal-Gruppe für Ridesharing. Wenn Du noch freie Plätze im Auto hast oder eine Mitfahrgelegenheit suchst, lade die Signal-App herunter, klicke den Link unten und schreibe eine Nachricht in die Gruppe.',
			link: 'https://signal.group/#CjQKIGVXIaBUBmvXV2rG6Ivtu-SQZDBtVoP8loZy-pqh6AAHEhBeQJohAYrSwKUHdXST38S7',
			isOpen: false
		},
		{
			question: 'Wie weit ist der Spaziergang?',
			answer:
				'Der Spaziergang ist ca. 1,6 km und hat eine leichte Steigung, ist aber grösstenteils eben (teils geteert, teils gut gepflegter Waldweg). Bitte bringt gutes Schuhwerk mit.',
			isOpen: false
		},
		{
			question: 'Was kann ich mitbringen?',
			answer:
				'Wir werden eine vegane Hochzeitstorte und ein veganes Kuchenbuffet haben. Wir freuen uns, wenn Leute vegane Kuchen mitbringen. Gib uns gerne per Signal oder E-Mail Bescheid, wenn Du einen mitbringst.',
			isOpen: false
		},
		{
			question: 'Wie kann ich mitmachen?',
			answer:
				'Wir planen bei unserer Zeremonie mit Bändern einen Knoten um unsere Hände zu machen, um unsere Verbindung zu symbolisieren. Es würde uns freuen, von ein paar Leuten ein Band dafür zu bekommen. Falls Du dazu etwas beisteuern möchtest, gestalte ein Band oder eine Kordel (ca. 1 m lang) und bringe es zur Hochzeit mit. Während des Brunchs habt ihr auch die Möglichkeit, vor Ort eines zu gestalten.',
			link: 'https://www.youtube.com/shorts/A6JDU8qO48Q',
			isOpen: false
		},
		{
			question: 'Wo kann ich übernachten?',
			answer:
				'Wir haben eine Liste mit empfohlenen Übernachtungsmöglichkeiten auf unserer Website unter "Übernachtung". Bitte buche frühzeitig.',
			link: '/uebernachtung',
			isOpen: false
		},
		{
			question: 'Was wünscht Ihr Euch?',
			answer: 'Du findest unsere Geschenkliste auf der Website unter "Geschenke".',
			link: '/geschenke',
			isOpen: false
		},
		{
			question: 'Wie lange dauert die Hochzeit?',
			answer: 'Die Veranstaltung ist open-end. Bleib so lange Du Lust und Spass hast.',
			isOpen: false
		},
		{
			question: 'Kann mein Hund mitkommen?',
			answer:
				'Ja. Rika wird auch da sein, aber es gibt genug Platz. Auf dem Hof gibt es viele freilaufende Hühner. Wenn Du nicht weisst, wie Dein Hund reagieren wird, bringe bitte einen Maulkorb mit.',
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
