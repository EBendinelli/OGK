<script>
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';
	let siteName = 'OTTOLENGHI GENERATIVE KITCHEN'; 
	let subTitle = 'RANDOMLY GENERATED OTTOLENGHI RECIPES'; 
	//let subTitle = 'MEGA DELICIOUS STUFF ';
</script>

<header>
	<div class="corner">
		<a href="https://github.com/sveltejs/kit">
			<img src={github} alt="GitHub" />
		</a>
	</div>

	<h1><a href="/"> {siteName} </a></h1>	

	<h2> {subTitle} </h2>

</header>

<style>
	header {
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	h1 {
		width: 100%;
		font-weight: bold;
		font-size: 65px;
		margin: 0px 0px 0px 0px;
	}

	h2 {
		width: 100%;
		color: #68d5dc;
		font-weight: bold;
		font-size: 35px;
		margin: 0px 0px 50px 0px;
		-webkit-text-stroke: 1.2px white;
		font-style: italic;
		letter-spacing: 0.3em;
	}

	p{
		color: #fff;	
		font-size: 25px;
	}

	.corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}

	h1 a{
		color: #e1251a;
		text-decoration: none;
	}

	h1 a{
		color: #e1251a;
		text-decoration: none;
	}	

</style>
