<script lang="ts">
	let counter = $state({ count: 0 });

	function counterHandler() {
		console.log($state.snapshot(counter));
		counter.count += 1;
		console.log($state.snapshot(counter));
	}
</script>

<div class="flex justify-center">
	<div class="container space-y-5">
		<h1 class="text-5xl font-mono">$state.snapshot</h1>
		<pre>
        {JSON.stringify($state.snapshot(counter), null, 2)}
      </pre>
		<button onclick={counterHandler} class="border px-4 py-1 rounded-md">snapshot</button>
	</div>
</div>
