<script lang="ts">
	import { enhance } from '$app/forms';

	let count = $state(0);

	interface Todo {
		id: number;
		title: string;
		completed: boolean;
	}
	let todos: Todo[] = $state([]);

	let title = $state('');

	function submitHandler() {
		todos = [...todos, { id: todos.length + 1, title: title, completed: false }];
	}
</script>

<div class="container flex justify-center">
	<div class="container space-y-5">
		<h1 class="text-5xl font-mono">$state</h1>
		<div class="border p-4">
			<p class="border px-3 w-fit mt-0">{count}</p>
			<button onclick={() => count++} class="border px-4 py-1 rounded-md">increment</button>
		</div>

		<div class="border p-4">
			<h2 class="text-3xl mt-0 font-mono">Todos</h2>
			<form method="POST" class="space-y-2" use:enhance>
				<label for="todo">Title</label> <br />
				<input type="text" class="border" name="title" id="todo" bind:value={title} />
				<br />
				<button type="submit" class="border px-4 py-1 rounded-md" onclick={() => submitHandler()}
					>add</button
				>
			</form>

			<ul class="space-y-2">
				{#each todos as todo (todo)}
					<li>
						<div class="flex gap-4 items-center">
							<div class="mt-0 text-2xl">{todo.title}</div>
							<div class="mt-0">{todo.completed}</div>
						</div>
					</li>
				{/each}
			</ul>
		</div>
	</div>
</div>
