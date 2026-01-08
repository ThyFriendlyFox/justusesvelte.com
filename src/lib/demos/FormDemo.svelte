<script>
	import { fade } from 'svelte/transition';
	
	let name = '';
	let email = '';
	let message = '';
	let submitted = false;
	
	$: characterCount = message.length;
	$: canSubmit = name.length > 0 && email.length > 0 && message.length > 0;
	
	function handleSubmit() {
		submitted = true;
		// In a real app, this would submit to a SvelteKit form action
		setTimeout(() => {
			submitted = false;
			name = '';
			email = '';
			message = '';
		}, 2000);
	}
</script>

<div class="demo">
	<h4>Two-Way Binding & Form Handling</h4>
	<p>Bind values with <code>bind:value</code>. No onChange handlers, no state management bullshit. Just bind and go.</p>
	
	{#if submitted}
		<div class="success-message" transition:fade={{ duration: 300 }}>
			<p>✓ Form submitted! (This is a demo, nothing actually happened.)</p>
		</div>
	{/if}
	
	<form on:submit|preventDefault={handleSubmit}>
		<div class="form-group">
			<label for="name">Name:</label>
			<input 
				id="name"
				type="text" 
				bind:value={name}
				placeholder="Your name"
			/>
		</div>
		
		<div class="form-group">
			<label for="email">Email:</label>
			<input 
				id="email"
				type="email" 
				bind:value={email}
				placeholder="your@email.com"
			/>
		</div>
		
		<div class="form-group">
			<label for="message">Message:</label>
			<textarea 
				id="message"
				bind:value={message}
				placeholder="Your message..."
				rows="4"
			></textarea>
			<span class="char-count">{characterCount} characters</span>
		</div>
		
		<button type="submit" disabled={!canSubmit || submitted}>
			{submitted ? 'Submitting...' : 'Submit'}
		</button>
	</form>
</div>

<style>
	.form-group {
		margin-bottom: 1rem;
	}
	
	.form-group label {
		display: block;
		margin-bottom: 0.5rem;
		font-weight: 600;
	}
	
	.form-group input,
	.form-group textarea {
		width: 100%;
		padding: 0.75rem;
		border: 2px solid var(--border-color);
		border-radius: 4px;
		background: var(--bg-color);
		color: var(--text-color);
		font-size: 1rem;
		font-family: inherit;
		transition: border-color 0.2s;
	}
	
	.form-group input:focus,
	.form-group textarea:focus {
		outline: none;
		border-color: var(--accent-color);
	}
	
	.char-count {
		display: block;
		margin-top: 0.25rem;
		font-size: 0.85rem;
		opacity: 0.7;
	}
	
	form button {
		background: var(--accent-color);
		color: white;
		border: none;
		padding: 0.75rem 2rem;
		border-radius: 4px;
		font-size: 1rem;
		font-weight: 600;
		cursor: pointer;
		transition: background 0.2s;
		width: 100%;
		margin-top: 0.5rem;
	}
	
	form button:hover:not(:disabled) {
		background: #ff5500;
	}
	
	form button:disabled {
		opacity: 0.5;
		cursor: not-allowed;
	}
	
	.success-message {
		background: #00cc00;
		color: white;
		padding: 1rem;
		border-radius: 4px;
		margin-bottom: 1rem;
		text-align: center;
	}
	
	.success-message p {
		margin: 0;
	}
</style>

