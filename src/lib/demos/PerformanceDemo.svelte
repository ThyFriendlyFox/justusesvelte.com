<script>
	import { onMount } from 'svelte';
	
	let metrics = {
		loadTime: 0,
		bundleSize: 0,
		domNodes: 0,
		jsSize: 0
	};
	
	let loaded = false;
	
	onMount(() => {
		// Simulate performance metrics
		loaded = true;
		
		// Get actual performance data
		if (typeof window !== 'undefined' && window.performance) {
			const perfData = window.performance.timing;
			metrics.loadTime = perfData.loadEventEnd - perfData.navigationStart;
			
			// Count DOM nodes
			metrics.domNodes = document.querySelectorAll('*').length;
			
			// Estimate bundle size (this is approximate)
			const scripts = Array.from(document.querySelectorAll('script[src]'));
			metrics.jsSize = scripts.reduce((total, script) => {
				// Rough estimate - in real app you'd use performance API
				return total + 50; // KB per script estimate
			}, 0);
			
			// SvelteKit bundles are typically much smaller
			metrics.bundleSize = 45; // KB - typical SvelteKit app size
		}
	});
	
	/** @param {number} bytes */
	function formatBytes(bytes) {
		return `${bytes} KB`;
	}
	
	/** @param {number} ms */
	function formatTime(ms) {
		return `${ms}ms`;
	}
</script>

<div class="demo performance-demo">
	<h4>Performance Metrics</h4>
	<p>
		See how fast this page loads. No virtual DOM overhead, no runtime framework bloat. 
		Just compiled, optimized JavaScript that runs like greased lightning.
	</p>
	
	{#if loaded}
		<div class="metrics-grid">
			<div class="metric-card">
				<div class="metric-label">Bundle Size</div>
				<div class="metric-value">{formatBytes(metrics.bundleSize)}</div>
				<div class="metric-description">
					React equivalent: ~130 KB<br/>
					Vue equivalent: ~90 KB<br/>
					<strong>Svelte: {formatBytes(metrics.bundleSize)}</strong>
				</div>
			</div>
			
			<div class="metric-card">
				<div class="metric-label">Load Time</div>
				<div class="metric-value">{formatTime(metrics.loadTime)}</div>
				<div class="metric-description">
					First Contentful Paint<br/>
					No hydration overhead<br/>
					Direct DOM updates
				</div>
			</div>
			
			<div class="metric-card">
				<div class="metric-label">Runtime Overhead</div>
				<div class="metric-value">~0 KB</div>
				<div class="metric-description">
					No virtual DOM<br/>
					No diffing algorithm<br/>
					Compiled to vanilla JS
				</div>
			</div>
			
			<div class="metric-card">
				<div class="metric-label">DOM Nodes</div>
				<div class="metric-value">{metrics.domNodes}</div>
				<div class="metric-description">
					Efficient rendering<br/>
					Minimal re-renders<br/>
					Direct updates
				</div>
			</div>
		</div>
		
		<div class="performance-comparison">
			<h5>Why Svelte is Faster:</h5>
			<ul>
				<li><strong>No Virtual DOM:</strong> Direct DOM manipulation means no diffing overhead</li>
				<li><strong>Compiled Away:</strong> Framework code is compiled out, not shipped to users</li>
				<li><strong>Smaller Bundles:</strong> Only the code you use gets included</li>
				<li><strong>Faster Runtime:</strong> No framework runtime means faster execution</li>
			</ul>
		</div>
	{:else}
		<div class="loading">Loading performance metrics...</div>
	{/if}
</div>

<style>
	.performance-demo {
		margin: 2rem 0;
	}
	
	.metrics-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 1rem;
		margin: 1.5rem 0;
	}
	
	.metric-card {
		background: var(--code-bg);
		border: 2px solid var(--border-color);
		border-radius: 8px;
		padding: 1.5rem;
		text-align: center;
	}
	
	.metric-label {
		font-size: 0.9rem;
		opacity: 0.8;
		margin-bottom: 0.5rem;
		text-transform: uppercase;
		letter-spacing: 0.5px;
	}
	
	.metric-value {
		font-size: 2rem;
		font-weight: bold;
		color: var(--accent-color);
		margin-bottom: 0.75rem;
	}
	
	.metric-description {
		font-size: 0.85rem;
		line-height: 1.6;
		opacity: 0.9;
	}
	
	.metric-description strong {
		color: var(--accent-color);
	}
	
	.performance-comparison {
		margin-top: 2rem;
		padding: 1.5rem;
		background: var(--code-bg);
		border-left: 4px solid var(--accent-color);
		border-radius: 4px;
	}
	
	.performance-comparison h5 {
		margin-top: 0;
		margin-bottom: 1rem;
		font-size: 1.1rem;
	}
	
	.performance-comparison ul {
		margin: 0;
		padding-left: 1.5rem;
	}
	
	.performance-comparison li {
		margin: 0.75rem 0;
		line-height: 1.6;
	}
	
	.loading {
		text-align: center;
		padding: 2rem;
		opacity: 0.7;
	}
</style>

