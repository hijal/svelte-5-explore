<script lang="ts">
	let person = $state.raw({
		name: 'Heraclitus',
		age: 22
	});

	function incrementAge() {
		person.age += 1;
	}

	function updatePerson() {
		person = {
			name: 'Heraclitus',
			age: 33
		};
	}

	let displayAge = $derived(person.age);
</script>

<div class="flex justify-center">
	<div class="container space-y-5">
		<h1 class="text-5xl font-mono">$state.raw</h1>

		<p>Current age: {displayAge}</p>

		<pre>
      {JSON.stringify(person, null, 2)}
    </pre>

		<div class="space-x-4">
			<button class="px-4 py-2 bg-blue-500 text-white rounded" onclick={incrementAge}>
				Increment Age
			</button>

			<button class="px-4 py-2 bg-green-500 text-white rounded" onclick={updatePerson}>
				Update Person
			</button>
		</div>
	</div>
</div>
