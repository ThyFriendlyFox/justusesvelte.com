<div class="demo file-structure-demo">
	<h4>File-Based Routing That Makes Sense</h4>
	<p>
		No route config files. No path arrays. No wondering where the fuck your route is defined. 
		Just create a file, get a route. It's that simple, you overthinking bastard.
	</p>
	
	<pre class="file-tree"><code>my-project/
├── src/
│   ├── lib/
│   │   ├── server/
│   │   │   └── [your server-only lib files]
│   │   └── [your lib files]
│   ├── params/
│   │   └── [your param matchers]
│   ├── routes/
│   │   ├── +page.svelte
│   │   ├── about/
│   │   │   └── +page.svelte
│   │   ├── blog/
│   │   │   ├── +page.svelte
│   │   │   └── [slug]/
│   │   │       └── +page.svelte
│   │   └── [your routes]
│   ├── app.html
│   ├── error.html
│   ├── hooks.client.js
│   ├── hooks.server.js
│   ├── service-worker.js
│   └── tracing.server.js
├── static/
│   └── [your static assets]
├── tests/
│   └── [your tests]
├── package.json
├── svelte.config.js
├── tsconfig.json
└── vite.config.js</code></pre>
	
	<div class="structure-explanation">
		<div class="explanation-item">
			<strong>No Route Config:</strong> Create <code>src/routes/about/+page.svelte</code> and you get <code>/about</code>. Done.
		</div>
		<div class="explanation-item">
			<strong>Dynamic Routes:</strong> Use <code>[slug]</code> or <code>[id]</code> in folder names for params. No regex needed.
		</div>
		<div class="explanation-item">
			<strong>Layouts:</strong> Add <code>+layout.svelte</code> to wrap child routes. No nested router components.
		</div>
		<div class="explanation-item">
			<strong>API Routes:</strong> Create <code>+server.js</code> files. Same file structure, same routing rules.
		</div>
	</div>
</div>

<style>
	.file-structure-demo {
		margin: 2rem 0;
	}
	
	.file-tree {
		background: var(--code-bg);
		border: 2px solid var(--border-color);
		border-radius: 8px;
		padding: 1.5rem;
		margin: 1.5rem 0;
		overflow-x: auto;
		font-family: 'Courier New', monospace;
		font-size: 0.9rem;
		line-height: 1.6;
		color: var(--text-color);
	}
	
	.file-tree code {
		background: transparent;
		padding: 0;
		border-radius: 0;
		font-family: inherit;
		font-size: inherit;
		color: inherit;
	}
	
	.structure-explanation {
		margin-top: 1.5rem;
		padding: 1rem;
		background: var(--code-bg);
		border-left: 4px solid var(--accent-color);
		border-radius: 4px;
	}
	
	.explanation-item {
		margin: 0.75rem 0;
		font-size: 0.95rem;
		line-height: 1.6;
	}
	
	.explanation-item code {
		background: var(--bg-color);
		padding: 0.2em 0.4em;
		border-radius: 3px;
		font-size: 0.9em;
	}
</style>
