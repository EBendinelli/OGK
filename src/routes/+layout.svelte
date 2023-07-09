<script>
	import Header from './Header.svelte';
	import { page } from '$app/stores';
	import './styles.css';
</script>

<div class="app">
	<Header />

	<main>
		<slot />
	</main>

	<footer>
		<nav>
			<ul>
				<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
					<a href="/">Recipe</a>
				</li>
				<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
					<a href="/about">About</a>
				</li>
			</ul>
		</nav>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	Header {
		flex: 1;
	}

	main {
		flex: 2;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 1rem;
		width: 100%;
		margin: 0 auto;
		box-sizing: border-box;
		background-color: #e1251a;
		color: #ffffff;
	}

	footer {
		display: flex;
		flex: 2;
		flex-direction: column;
		justify-content: center;
		align-items: end;
		padding: 30px;
	}

	footer a {
		color: var(--color-theme-1);
		color: #eb533b;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}

	nav {
		display: flex;
	}


	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: right;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	}
</style>
