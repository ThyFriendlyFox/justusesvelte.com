<script>
	import { fade, slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	
	let visible = true;
	let items = ['Svelte', 'is', 'fucking', 'awesome'];
	let listItems = [...items];
	
	function toggle() {
		visible = !visible;
	}
	
	function addItem() {
		const newItem = `Item ${listItems.length + 1}`;
		listItems = [...listItems, newItem];
	}
	
	function removeItem() {
		listItems = listItems.slice(0, -1);
	}
</script>

<div class="demo">
	<h4>Smooth Transitions & Animations</h4>
	<p>Built-in transitions that just work. No animation libraries needed, you lazy fuck.</p>
	
	<div class="transition-controls">
		<button on:click={toggle}>
			{visible ? 'Hide' : 'Show'} Box
		</button>
		<button on:click={addItem}>Add Item</button>
		<button on:click={removeItem} disabled={listItems.length === 0}>
			Remove Item
		</button>
	</div>
	
	{#if visible}
		<div class="box" transition:fade={{ duration: 300 }}>
			<p>Fade transition, motherfucker!</p>
		</div>
	{/if}
	
	<div class="list-container">
		{#each listItems as item, i (item)}
			<div 
				class="list-item"
				transition:slide={{ duration: 300, easing: quintOut }}
			>
				{item}
			</div>
		{/each}
	</div>
</div>

<style>
	.transition-controls {
		display: flex;
		gap: 0.5rem;
		margin-bottom: 1rem;
		flex-wrap: wrap;
	}
	
	.transition-controls button {
		background: var(--accent-color);
		color: white;
		border: none;
		padding: 0.5rem 1rem;
		border-radius: 4px;
		cursor: pointer;
		font-size: 0.9rem;
		transition: background 0.2s;
	}
	
	.transition-controls button:hover:not(:disabled) {
		background: #ff5500;
	}
	
	.transition-controls button:disabled {
		opacity: 0.5;
		cursor: not-allowed;
	}
	
	.box {
		background: var(--accent-color);
		color: white;
		padding: 2rem;
		border-radius: 8px;
		text-align: center;
		margin: 1rem 0;
	}
	
	.list-container {
		margin-top: 1rem;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}
	
	.list-item {
		background: var(--bg-color);
		border: 1px solid var(--border-color);
		padding: 0.75rem 1rem;
		border-radius: 4px;
	}
</style>

