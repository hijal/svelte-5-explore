<script lang="ts">
	let person: {
		name: string;
		age: number;
	} = $state.raw({
		name: 'Heraclitus',
		age: 22
	});

	person.age += 1;

	person = {
		name: 'Heraclitus',
		age: 33
	};
</script>

<div class="flex justify-center">
	<div class="container space-y-5">
		<h1 class="text-5xl font-mono">$state.raw</h1>

		<pre>
      {JSON.stringify(person, null, 2)}
    </pre>
	</div>
</div>
