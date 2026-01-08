<script>
	let count = 0;
	let doubled = 0;
	
	// Reactive statement - automatically updates when count changes
	$: doubled = count * 2;
	$: isEven = count % 2 === 0;
	
	function increment() {
		count += 1;
	}
	
	function decrement() {
		count -= 1;
	}
</script>

<div class="demo">
	<h4>Reactive Counter with $: Statements</h4>
	<p>Watch how <code>doubled</code> and <code>isEven</code> update automatically when <code>count</code> changes. No hooks, no dependency arrays, just magic.</p>
	
	<div class="counter-display">
		<button on:click={decrement}>−</button>
		<span class="count" class:even={isEven} class:odd={!isEven}>
			{count}
		</span>
		<button on:click={increment}>+</button>
	</div>
	
	<div class="reactive-output">
		<p>Doubled: <strong>{doubled}</strong></p>
		<p>Is even: <strong>{isEven ? 'Yes' : 'No'}</strong></p>
	</div>
</div>

<style>
	.demo {
		border: 2px solid var(--border-color);
		border-radius: 8px;
		padding: 1.5rem;
		margin: 2rem 0;
		background: var(--code-bg);
	}
	
	.demo h4 {
		margin-top: 0;
		margin-bottom: 0.5rem;
		font-size: 1.2rem;
	}
	
	.demo p {
		margin-bottom: 1rem;
		font-size: 0.95rem;
		opacity: 0.9;
	}
	
	.counter-display {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1rem;
		margin: 1.5rem 0;
	}
	
	.counter-display button {
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
	
	.counter-display button:hover {
		transform: scale(1.1);
		background: #ff5500;
	}
	
	.counter-display button:active {
		transform: scale(0.95);
	}
	
	.count {
		font-size: 3rem;
		font-weight: bold;
		min-width: 4rem;
		text-align: center;
		transition: color 0.3s;
	}
	
	.count.even {
		color: #00cc00;
	}
	
	.count.odd {
		color: #ff3e00;
	}
	
	.reactive-output {
		display: flex;
		gap: 2rem;
		justify-content: center;
		margin-top: 1rem;
	}
	
	.reactive-output p {
		margin: 0;
		font-size: 1rem;
	}
</style>

