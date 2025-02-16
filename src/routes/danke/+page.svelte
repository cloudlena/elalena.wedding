<script lang="ts">
	import { browser } from '$app/environment';

	let gift = 'Geschenk';
	if (browser) {
		const urlParams = new URLSearchParams(window.location.search);
		gift = urlParams.get('gift') || '';
	}
</script>

<div class="mx-auto max-w-4xl">
	<div class="mt-12 mb-24 text-center">
		<h1 class="mb-4 text-4xl md:text-6xl">Vielen Dank!</h1>
	</div>

	<div class="mb-24 p-6 text-center text-2xl md:text-3xl">
		Bitte benutze Twint oder überweise den gewünschten Betrag mit dem an:<br /><br />

		<p class="font-mono">
			Lena Fuhrimann & Raphaela Seeger<br />
			Tavelweg 25<br />
			3006 Bern<br /><br />

			IBAN: CH34 0830 7000 5999 8131 8<br />
			SWIFT-Code/BIC: HYPLCH22<br /><br />

			Vermerk: {gift}
		</p>
	</div>
</div>
