<script lang="ts">
	let isComing = $state(true);
</script>

<div class="mb-24 p-6 text-center text-2xl md:text-4xl">
	<h2 class="mb-4 text-4xl md:text-7xl">Teilnahme</h2>

	<form class="mx-auto max-w-sm" action="https://formspree.io/f/mdkaawwe" method="POST">
		<div class="mb-4">
			<label for="name" class="mb-2 block text-left">Name</label>
			<input
				id="name"
				name="name"
				class="block w-full rounded-sm border border-gray-300 bg-white p-2 focus:border-green-600 focus:ring-green-600"
				required
			/>
		</div>
		<div class="mb-8">
			<label for="name" class="mb-2 block text-left">E-Mail</label>
			<input
				id="email"
				name="email"
				type="email"
				class="block w-full rounded-sm border border-gray-300 bg-white p-2 focus:border-green-600 focus:ring-green-600"
				required
			/>
		</div>
		<div class="mb-6 flex items-start gap-4 px-4">
			<div class="flex h-5 items-center">
				<input
					id="yes"
					type="radio"
					name="rsvp"
					bind:group={isComing}
					value={true}
					class="h-4 w-4 rounded-sm border border-gray-300 bg-gray-50 focus:ring-3 focus:ring-blue-300"
					required
					checked
				/>
			</div>
			<label for="yes" class="ms-2 font-medium">Ich bin dabei</label>
		</div>
		<div class="mb-8 flex items-start gap-4 px-4">
			<div class="flex h-5 items-center">
				<input
					id="no"
					type="radio"
					name="rsvp"
					bind:group={isComing}
					value={false}
					class="h-4 w-4 rounded-sm border border-gray-300 bg-gray-50 focus:ring-3 focus:ring-blue-300"
					required
				/>
			</div>
			<label for="no" class="ms-2 font-medium">Ich kann nicht kommen</label>
		</div>
		{#if isComing}
			<div class="mb-8">
				<label for="guests" class="mb-2 block text-left">Anzahl Erwachsene</label>
				<input
					id="guests"
					name="guests"
					type="number"
					value="1"
					class="block w-full rounded-sm border border-gray-300 bg-white p-2 focus:border-green-600 focus:ring-green-600"
					required
				/>
			</div>
		{/if}
		<div class="mb-8">
			<label for="remarks" class="mb-2 block text-left">Fragen / Anmerkungen</label>
			<textarea
				name="remarks"
				id="remarks"
				class="block w-full rounded-sm border border-gray-300 bg-white p-2 focus:border-green-600 focus:ring-green-600"
			></textarea>
		</div>
		<button
			type="submit"
			class="w-full cursor-pointer rounded-lg bg-green-900 px-5 py-2 text-center text-white hover:bg-green-700 focus:ring-4 focus:ring-green-600 focus:outline-none"
			>Absenden</button
		>
	</form>
</div>
