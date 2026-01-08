<script>
	import ReactiveCounter from '$lib/demos/ReactiveCounter.svelte';
	import TransitionDemo from '$lib/demos/TransitionDemo.svelte';
	import StoreDemo from '$lib/demos/StoreDemo.svelte';
	import FormDemo from '$lib/demos/FormDemo.svelte';
	import FileStructure from '$lib/demos/FileStructure.svelte';
	import PerformanceDemo from '$lib/demos/PerformanceDemo.svelte';
</script>

<svelte:head>
	<title>JUST FUCKING USE SVELTE - Stop Overthinking It, Use Svelte</title>
	<meta name="description" content="Stop overthinking it. Just use Svelte. Learn why Svelte is better than React, Vue, or vanilla JavaScript. See live demos of reactive statements, transitions, stores, and file-based routing." />
	<meta name="keywords" content="Svelte, SvelteKit, JavaScript framework, web development, React alternative, Vue alternative, frontend framework, reactive programming, web components, SSR, SSG, file-based routing" />
	<meta name="author" content="thyfriendlyfox" />
	<meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1" />
	<meta name="googlebot" content="index, follow" />
	<meta name="language" content="English" />
	<meta name="revisit-after" content="7 days" />
	<meta name="theme-color" content="#1a1a1a" />
	
	<!-- Open Graph / Facebook -->
	<meta property="og:type" content="website" />
	<meta property="og:url" content="https://justusesvelte.com/" />
	<meta property="og:title" content="JUST FUCKING USE SVELTE - Stop Overthinking It, Use Svelte" />
	<meta property="og:description" content="Stop overthinking it. Just use Svelte. Learn why Svelte is better than React, Vue, or vanilla JavaScript. See live demos of reactive statements, transitions, stores, and file-based routing." />
	<meta property="og:site_name" content="Just Use Svelte" />
	<meta property="og:locale" content="en_US" />
	
	<!-- Twitter Card -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:url" content="https://justusesvelte.com/" />
	<meta name="twitter:title" content="JUST FUCKING USE SVELTE - Stop Overthinking It, Use Svelte" />
	<meta name="twitter:description" content="Stop overthinking it. Just use Svelte. Learn why Svelte is better than React, Vue, or vanilla JavaScript. See live demos of reactive statements, transitions, stores, and file-based routing." />
	<meta name="twitter:creator" content="@thyfriendlyfox" />
	<meta name="twitter:site" content="@thyfriendlyfox" />
	
	<!-- Canonical URL -->
	<link rel="canonical" href="https://justusesvelte.com/" />
	
	<!-- Alternate languages (if you have translations) -->
	<link rel="alternate" hreflang="en" href="https://justusesvelte.com/" />
	<link rel="alternate" hreflang="x-default" href="https://justusesvelte.com/" />
	
	<!-- Preconnect to external domains for performance -->
	<link rel="preconnect" href="https://github.com" crossorigin="anonymous" />
	<link rel="preconnect" href="https://twitter.com" crossorigin="anonymous" />
	
	<!-- DNS Prefetch -->
	<link rel="dns-prefetch" href="https://github.com" />
	<link rel="dns-prefetch" href="https://twitter.com" />
	
	<!-- Sitemap -->
	<link rel="sitemap" type="application/xml" href="/sitemap.xml" />
	
	<!-- Structured Data - Website -->
	{@html `<script type="application/ld+json">
	{
		"@context": "https://schema.org",
		"@type": "WebSite",
		"name": "Just Use Svelte",
		"url": "https://justusesvelte.com/",
		"description": "Stop overthinking it. Just use Svelte. Learn why Svelte is better than React, Vue, or vanilla JavaScript.",
		"author": {
			"@type": "Person",
			"name": "thyfriendlyfox",
			"url": "https://github.com/thyfriendlyfox",
			"sameAs": [
				"https://twitter.com/thyfriendlyfox",
				"https://github.com/thyfriendlyfox"
			]
		},
		"potentialAction": {
			"@type": "SearchAction",
			"target": "https://justusesvelte.com/?q={search_term_string}",
			"query-input": "required name=search_term_string"
		}
	}
	</script>`}
	
	<!-- Structured Data - Article -->
	{@html `<script type="application/ld+json">
	{
		"@context": "https://schema.org",
		"@type": "Article",
		"headline": "JUST FUCKING USE SVELTE - Stop Overthinking It, Use Svelte",
		"description": "Stop overthinking it. Just use Svelte. Learn why Svelte is better than React, Vue, or vanilla JavaScript. See live demos of reactive statements, transitions, stores, and file-based routing.",
		"url": "https://justusesvelte.com/",
		"datePublished": "2026-01-08",
		"dateModified": "2026-01-08",
		"author": {
			"@type": "Person",
			"name": "thyfriendlyfox",
			"url": "https://github.com/thyfriendlyfox"
		},
		"publisher": {
			"@type": "Person",
			"name": "thyfriendlyfox",
			"url": "https://github.com/thyfriendlyfox"
		},
		"mainEntityOfPage": {
			"@type": "WebPage",
			"@id": "https://justusesvelte.com/"
		},
		"keywords": "Svelte, SvelteKit, JavaScript framework, web development, React alternative, Vue alternative, frontend framework",
		"articleSection": "Web Development",
		"inLanguage": "en-US"
	}
	</script>`}
	
	<!-- Structured Data - TechArticle -->
	{@html `<script type="application/ld+json">
	{
		"@context": "https://schema.org",
		"@type": "TechArticle",
		"headline": "Why You Should Use Svelte Instead of React or Vue",
		"description": "Learn why Svelte is the best choice for modern web development. Compare Svelte vs React, Vue, and vanilla JavaScript with live demos.",
		"author": {
			"@type": "Person",
			"name": "thyfriendlyfox"
		},
		"dependencies": "Svelte, SvelteKit",
		"proficiencyLevel": "Beginner",
		"about": {
			"@type": "Thing",
			"name": "Svelte Framework",
			"description": "A modern JavaScript framework for building user interfaces"
		}
	}
	</script>`}
</svelte:head>

<div class="container">
	<nav aria-label="Main navigation">
		<ul>
			<li><a href="#content">Content</a></li>
			<li><a href="#what">What the fuck is this about?</a></li>
			<li><a href="#why">Why the fuck would I use Svelte?</a></li>
			<li><a href="#demos">See Svelte in Action</a></li>
			<li><a href="#bloat">But what about the fucking bloat?</a></li>
			<li><a href="#when">When should I just fucking use Svelte?</a></li>
			<li><a href="#problem">The real fucking problem isn't Svelte. It's you.</a></li>
			<li><a href="#footer">Footer</a></li>
		</ul>
	</nav>

	<main id="content" itemscope itemtype="https://schema.org/Article">
		<h1 itemprop="headline">JUST FUCKING USE SVELTE</h1>
		<p style="font-size: 1.3rem; margin-bottom: 2rem;" itemprop="alternativeHeadline">
			(OR ANY FRAMEWORK, YOU GODDAMN LUDDITE)
		</p>

		<section id="what">
			<h2>WHAT THE FUCK IS THIS ABOUT?</h2>
			<p>
				Look, I get it. You saw that other site. "HTML is king", "Keep it simple, stupid", 
				"My GeoCities page from '98 still loads faster than your SPA." Fucking adorable. 
				Like a toddler proudly showing off a mud pie.
			</p>
			<p>
				It's a nice sentiment, like wishing we could all go back to bartering with seashells 
				instead of dealing with the goddamn stock market. But the web isn't just a collection 
				of fucking pamphlets anymore, you fossil. It's where work gets done, where communities 
				are built, where complex interactions happen. You know, shit that actually <em>does</em> 
				something beyond displaying your "Fucking beautiful button."
			</p>
			<p>
				This is about acknowledging that sometimes, complexity is not a choice, it's a fucking 
				requirement. And when that complexity hits, trying to wrangle it with 
				<code>document.getElementById</code> and a prayer is like trying to build a goddamn 
				space shuttle with fucking popsicle sticks and glue. You might get something that looks 
				vaguely shuttle-shaped, but it'll be a wobbly, unmaintainable, terrifying piece of shit 
				that explodes on the launchpad.
			</p>
			<p>
				This is a call to embrace the tools built by smart motherfuckers to solve the hard problems 
				so you can focus on building your cool shit, not reinventing the goddamn wheel for the 
				87th time this sprint, you stubborn jackass.
			</p>
		</section>

		<section id="why">
			<h2>WHY THE FUCK WOULD I USE SVELTE INSTEAD OF REACT (OR VUE, OR ANGULAR)?</h2>
			<p>
				Because you're not just displaying static text from a fucking stone tablet, are you? 
				You want to build something interactive, something dynamic, something that doesn't make 
				your users want to gouge their eyes out with a rusty spoon. You want to build an 
				<em>application</em>, not a fucking flyer.
			</p>
			<p>
				But wait, you say. "Why Svelte specifically? React has a bigger ecosystem! Vue is more 
				popular! Angular has Google backing!" Yeah, and your toddler has crayons. Adorable, but 
				not exactly the tools for designing a fucking skyscraper, are they?
			</p>
			<p>
				Here's why you should just fucking use Svelte (or at least consider it, you troglodyte):
			</p>

			<h3>NO VIRTUAL DOM BULLSHIT, YOU CLUELESS APE!</h3>
			<p>
				React and Vue use a virtual DOM. That means they build a whole goddamn representation of 
				your UI in JavaScript, then compare it to the real DOM, then figure out what changed, 
				then update the real DOM. It's like hiring a fucking translator to tell you what you 
				already know in your own language. Svelte compiles your components into tiny, 
				optimized vanilla JavaScript that updates the DOM directly. No middleman, no overhead, 
				no bullshit. It's like the difference between ordering food through a fucking app that 
				takes a 30% cut versus just walking into the restaurant and ordering directly.
			</p>
			<p>
				The result? Smaller bundle sizes, faster runtime performance, and code that actually 
				makes sense when you read it. Revolutionary fucking concept, I know.
			</p>

			<h3>REACTIVE STATEMENTS THAT ACTUALLY MAKE SENSE, MOTHERFUCKER!</h3>
			<p>
				In React, you're constantly wrestling with <code>useState</code>, <code>useEffect</code>, 
				<code>useMemo</code>, <code>useCallback</code>, and a dozen other hooks that make your 
				code look like a fucking Rube Goldberg machine. Svelte's reactivity is built into the 
				language itself. Just use <code>$:</code> and boom, reactive statements. Change a variable? 
				Everything that depends on it updates automatically. No hooks, no dependency arrays, no 
				"why the fuck isn't this updating?" debugging sessions at 3 AM.
			</p>
			<p>
				It's like the difference between manually cranking a car engine versus just turning a key. 
				Both get you moving, but one doesn't make you want to throw your laptop out the window.
			</p>
			
			
			<section id="demos" style="margin-top: 4rem;">
				<h2 style="margin-top: 0;">SEE SVELTE IN ACTION, YOU SKEPTICAL BASTARD</h2>
				<p>
					Don't just take my word for it. Play with these demos and see how fucking easy it is 
					to build interactive shit with Svelte. No virtual DOM overhead, no hook complexity, 
					just clean, reactive code that makes sense.
				</p>
			</section>
			
			<ReactiveCounter />

			<h3>COMPONENTS THAT ARE ACTUALLY JUST HTML, CSS, AND JS, YOU DELUSIONAL TWIT.</h3>
			<p>
				Remember when web development was about HTML, CSS, and JavaScript? Svelte components 
				are exactly that. One file, three sections. No JSX weirdness, no template syntax that 
				makes you question your life choices, no separate style files that get out of sync. 
				It's all there, scoped automatically, working together like they were meant to.
			</p>
			<p>
				You think you're gonna build a real-time collaborative editor, a dynamic trading dashboard, 
				or an enterprise-grade project management tool with pure HTML and vanilla JS? You're 
				dreaming, you magnificent simpleton. But at least with Svelte, you're using tools that 
				feel familiar instead of learning a whole new language just to write a fucking button.
			</p>
			
			<FileStructure />
			
			<TransitionDemo />
			
			<StoreDemo />
			
			<FormDemo />

			<h3>SMALLER BUNDLES, FASTER LOADS, LESS BULLSHIT.</h3>
			<p>
				Because Svelte compiles away the framework, you ship less JavaScript. A lot less. Your 
				users get faster page loads, better performance on shitty devices, and you get to feel 
				superior about your bundle size. It's a win-win, you short-sighted goon.
			</p>
			<p>
				React's runtime is like carrying around a fucking toolbox everywhere you go, even when 
				you just need a screwdriver. Svelte gives you exactly the tools you need, nothing more, 
				nothing less. It's like the difference between a Swiss Army knife and a goddamn hardware 
				store strapped to your back.
			</p>
			
			<PerformanceDemo />

			<h3>ACCESSIBILITY AT SCALE? GOOD LUCK WITH YOUR "SEMANTIC" DIV SOUP AND PRAYERS, ASSHOLE.</h3>
			<p>
				"Just use semantic HTML!" they shriek, like they've discovered the goddamn Rosetta Stone. 
				Fucking groundbreaking. That's Web Dev 101, you patronizing prick.
			</p>
			<p>
				But what happens when your "simple" HTML tags aren't enough for the complex, custom UI your 
				application <em>actually needs</em>? Think custom data grids that sort and filter, accessible 
				comboboxes that don't suck, or tree views that a screen reader can actually navigate. You 
				think slapping <code>role="button"</code> on a <code>&lt;div&gt;</code> and calling it a day 
				makes your app accessible? Get the fuck out.
			</p>
			<p>
				Real accessibility for complex widgets means meticulous ARIA attributes, robust focus 
				management, and proper keyboard navigation. With Svelte, you build an <em>accessible component</em> 
				once, nail all that shit, and then reuse it, ensuring consistency. Or are you gonna tell me 
				you <em>enjoy</em> manually managing <code>aria-expanded</code> on 50 different accordions, 
				you goddamn masochist?
			</p>

			<h3>DEVELOPER EXPERIENCE ACTUALLY FUCKING MATTERS, UNLESS YOU ENJOY PAIN.</h3>
			<p>
				Hot Module Replacement? See your changes instantly without losing state. TypeScript support 
				that doesn't make you want to cry? Check. A compiler that catches errors before runtime? 
				Fucking revolutionary. SvelteKit for full-stack apps with server-side rendering, routing, 
				and API routes all in one place? It's like having a complete workshop instead of a scattered 
				toolbox across five different garages.
			</p>
			<p>
				Stop pretending that wrestling with Webpack configs, Babel transforms, and a dozen 
				different build tools is some noble, character-building pursuit. It's just fucking stupid. 
				Svelte's tooling is simple, fast, and it just works.
			</p>

			<h3>PERFORMANCE ISN'T JUST ABOUT INITIAL LOAD LIKE SOME PRIMITIVE PAGE SPEED FETISHIST, 
				IT'S ABOUT PERCEIVED PERFORMANCE AND INTERACTION, YOU SHORT-SIGHTED GOON.</h3>
			<p>
				"My HTML site loads in 50ms!" Cool. Now add user login, dynamic content, filtering, 
				sorting, and real-time updates without the page shitting itself.
			</p>
			<p>
				Svelte, especially when paired with SvelteKit, gives you code-splitting (only load the 
				JS you need for this page, not the whole goddamn phonebook), server-side rendering (SSR) 
				or static site generation (SSG) for fast initial loads <em>and</em> dynamic capabilities, 
				and client-side navigation that feels instantaneous. You can build a lightning-fast 
				<em>application</em>, not just a fast document that does fuck-all.
			</p>
			<p>
				And because Svelte compiles to vanilla JS, your runtime performance is better than frameworks 
				that ship their entire runtime. It's like the difference between a race car and a fucking 
				tractor. Both can move, but one is built for speed.
			</p>
		</section>

		<section id="bloat">
			<h2>BUT WHAT ABOUT THE FUCKING BLOAT? THE JAVASCRIPT OVERLOAD? MY USERS ARE ON DIAL-UP IN ANTARCTICA!</h2>
			<p>
				Yes, a "Hello World" in a framework is bigger than a "Hello World" in HTML. 
				<strong>No shit, Sherlock.</strong> Are you building a fucking "Hello World" app for production? 
				If you're building a five-page static brochure site for your aunt's dog-walking business that 
				hasn't had a customer since 2003, then yes, for the love of God, just fucking use HTML and 
				some CSS. That other site is right about that. You don't need a fucking bazooka to swat a fly.
			</p>
			<p>
				But if you're building:
			</p>
			<ul>
				<li>A SaaS platform</li>
				<li>An e-commerce site with a complex cart and user accounts</li>
				<li>A social media feed</li>
				<li>A project management tool</li>
				<li>A data visualization dashboard</li>
				<li>Anything with significant client-side interactivity and state that needs to, you know, <em>work</em></li>
			</ul>
			<p>
				...then the "bloat" of a framework is the cost of doing complex business, you cheap bastard. 
				And Svelte helps you mitigate that cost better than most. It's about choosing the right fucking 
				tool for the right fucking job, not stubbornly using a screwdriver when you need a goddamn 
				sledgehammer.
			</p>
			<p>
				Plus, Svelte's compiled output is typically smaller than React or Vue equivalents. So if you're 
				worried about bundle size, Svelte is actually one of your better options, you paranoid fuck.
			</p>
		</section>

		<section id="when">
			<h2>SO, WHEN SHOULD I JUST FUCKING USE SVELTE, YOU SLOW LEARNER?</h2>
			<ul>
				<li>When your application has <strong>non-trivial client-side state</strong> that needs to be managed.</li>
				<li>When you need <strong>reusable UI components</strong> to build a consistent and maintainable interface.</li>
				<li>When you're building a <strong>Single Page Application</strong> or something that <em>feels</em> like an application rather than a document.</li>
				<li>When you're working in a <strong>team</strong> and need a shared structure and patterns.</li>
				<li>When the <strong>complexity of the interactions</strong> would lead to unmanageable spaghetti code in vanilla JS.</li>
				<li>When you want <strong>better performance</strong> and smaller bundles than React or Vue.</li>
				<li>When you want a <strong>simpler mental model</strong> than React's hooks or Vue's options API.</li>
				<li>When <strong>developer velocity</strong> for complex features is more critical than shaving off every last kilobyte for a mostly static page.</li>
			</ul>
		</section>

		<section id="problem">
			<h2>THE REAL FUCKING PROBLEM ISN'T SVELTE. IT'S YOU, YOU MISGUIDED FOOL.</h2>
			<p>
				It's developers using a goddamn nuclear bomb to crack a nut. It's cargo-culting the latest 
				tech without understanding why. It's trying to build a simple fucking contact form with 
				microservices, Kubernetes, and a team of twenty, when a mailto link would have done the job. 
				<strong>It's like using a fucking military-grade flamethrower to light your grandma's birthday 
				candles - utter goddamn overkill, you clueless fuck.</strong>
			</p>
			<p>
				But don't throw the fucking baby out with the bathwater just because some idiots don't know 
				how to use a power tool without cutting their own dicks off. Svelte and its ilk are powerful 
				tools that solve real, complex problems. The problem isn't the tool; it's the idiot wielding 
				it inappropriately.
			</p>
			<p>
				So, for your next complex, interactive, data-driven web application... for the love of all that 
				is holy, <strong>JUST FUCKING USE SVELTE</strong>. Stop pretending like you're too pure for it, 
				or that your "artisanal" vanilla JS is anything other than a cry for help. Your users (and your 
				future self trying to maintain your "hand-crafted" nightmare) will thank you.
			</p>
			<p>
				Now get back to work, and build something fucking amazing, not just another HTML monument to 
				your own stubbornness.
			</p>
		</section>
	</main>

	<footer id="footer" itemscope itemtype="https://schema.org/WPFooter">
		<p><strong>Created by:</strong></p>
		<p itemprop="author" itemscope itemtype="https://schema.org/Person">
			<span itemprop="name">thyfriendlyfox</span>
			(<a href="https://github.com/thyfriendlyfox" target="_blank" rel="noopener author me" itemprop="url">GitHub</a> / 
			<a href="https://twitter.com/thyfriendlyfox" target="_blank" rel="noopener author me" itemprop="sameAs">Twitter</a>)
		</p>
		<p style="margin-top: 1rem;">
			Inspired by <a href="https://justfuckingusereact.com/" target="_blank" rel="noopener">justfuckingusereact.com</a> 
			and <a href="https://justfuckingusehtml.com/" target="_blank" rel="noopener">justfuckingusehtml.com</a>
		</p>
		<p>
			<strong>View the source code on <a href="https://github.com/thyfriendlyfox/justusesvelte.com" target="_blank" rel="noopener">GitHub</a></strong>
		</p>
		<p style="margin-top: 1rem; font-size: 0.9rem; color: var(--text-color); opacity: 0.7;">
			© 2026
		</p>
	</footer>
</div>

