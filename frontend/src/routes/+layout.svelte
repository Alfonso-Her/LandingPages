<script lang="ts">
	import "../app.css";
	let { children } = $props();
</script>

<div class="app-container">
	<header class="navbar">
		<div class="nav-content">
			<a href="/" class="brand">LandingPages</a>
			<nav class="nav-links">
				<a href="/" class="nav-link">Builder</a>
				<a href="/debug" class="nav-link">Design System</a>
			</nav>
		</div>
	</header>

	<main class="main-content">
		{@render children()}
	</main>
</div>

<style>
	.app-container {
		min-height: 100vh;
		background-color: var(--color-bg);
		color: var(--color-text);
		font-family: var(--font-sans);
	}

	.navbar {
		background-color: var(--color-white);
		border-bottom: 1px solid var(--color-border);
		padding: var(--spacing-md) 0;
	}

	.nav-content {
		width: 100%;
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 var(--spacing-md);
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.brand {
		font-size: 1.25rem;
		font-weight: 700;
		color: var(--color-primary);
		text-decoration: none;
	}

	.nav-links {
		display: flex;
		gap: var(--spacing-lg);
	}

	.nav-link {
		color: var(--color-text);
		text-decoration: none;
		font-weight: 500;
		transition: color 0.2s;
	}

	.nav-link:hover {
		color: var(--color-primary);
	}

	.main-content {
		width: 100%;
		max-width: 1200px;
		margin: 0 auto;
		padding: var(--spacing-xl) var(--spacing-md);
	}
</style>
