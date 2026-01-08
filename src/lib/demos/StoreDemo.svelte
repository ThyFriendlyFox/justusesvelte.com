<script>
	import { writable } from 'svelte/store';
	
	// Create a writable store
	const count = writable(0);
	
	// Derived store - automatically updates when count changes
	import { derived } from 'svelte/store';
	const doubled = derived(count, $count => $count * 2);
	
	function increment() {
		count.update(n => n + 1);
	}
	
	function decrement() {
		count.update(n => n - 1);
	}
	
	function reset() {
		count.set(0);
	}
</script>

<div class="demo">
	<h4>Stores for Global State</h4>
	<p>Share state across components without prop drilling or context hell. Just subscribe with <code>$store</code>.</p>
	
	<div class="store-display">
		<button on:click={decrement}>−</button>
		<span class="store-count">{$count}</span>
		<button on:click={increment}>+</button>
	</div>
	
	<div class="store-output">
		<p>Count: <strong>{$count}</strong></p>
		<p>Doubled (derived): <strong>{$doubled}</strong></p>
	</div>
	
	<button class="reset-btn" on:click={reset}>Reset</button>
</div>

<style>
	.store-display {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1rem;
		margin: 1.5rem 0;
	}
	
	.store-display button {
		background: var(--accent-color);
		color: white;
		border: none;
		border-radius: 50%;
		width: 3rem;
		height: 3rem;
		font-size: 1.5rem;
		cursor: pointer;
		transition: transform 0.2s, background 0.2s;
		font-weight: bold;
	}
	
	.store-display button:hover {
		transform: scale(1.1);
		background: #ff5500;
	}
	
	.store-count {
		font-size: 3rem;
		font-weight: bold;
		min-width: 4rem;
		text-align: center;
		color: var(--accent-color);
	}
	
	.store-output {
		display: flex;
		gap: 2rem;
		justify-content: center;
		margin: 1rem 0;
	}
	
	.store-output p {
		margin: 0;
		font-size: 1rem;
	}
	
	.reset-btn {
		background: transparent;
		border: 2px solid var(--border-color);
		color: var(--text-color);
		padding: 0.5rem 1rem;
		border-radius: 4px;
		cursor: pointer;
		margin-top: 0.5rem;
		transition: all 0.2s;
	}
	
	.reset-btn:hover {
		background: var(--border-color);
	}
</style>

