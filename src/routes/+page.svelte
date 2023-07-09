<script>
	let recipeName = '';
	let recipeNames = [
		'Burnt aubergine with pickled zatar yoghurt',
		'Roasted pickles on cream cheese lemon',
		'Butter poached peaches with sweat and sour dressing',
		];

	let mainVeggie = [
		'Aubergines', 
		'Tomatoes', 
		'kohlrabi', 
		'Courgettes', 
		'Sweet Potatoes', 
		'Butternut Squash', 
		'Carrots', 
		'Asparagus', 
		'Brussels sprouts', 
		'Beetroots', 
		'Cabage', 
		'Cauliflower', 
		'Celriac', 
		'Cucumber', 
		'Kale', 
		'Mushrooms', 
		'Peppers', 
		'Potatoes', 
		'Swede',	
		'Swiss Chards',
		'Rainbow Chards',	
		'Avocadoes',	
		'Swede',
		];

	let connector = [
		'With',
		'And',
		'On',
		'Over',
	]

	let sideVeggie = [
		'Spinach', 
		'Mushrooms', 
		'Red Onions', 
		'Radishes', 
		'Spring Onions', 
		'Shallots', 
		'Sweet Corn', 
		'Lemon'
		];

	let carbs = [
		'Lentils',
		'Chickpeas',
		'White Beans',
		'Butter Beans',
		'Pasta',
		'Rice',
		'Pearl Barley',
		'Orzo',
		'Bulgur'
		];

	let technique = [
		'Pickled',
		'Roasted',
		'Burnt',
		'Cured',
		'Smoked',
		'Slow cooked',
		'Preserved',
		'Braised',
		'Grilled',
		];

	let qualifier = [
		'Smoky',
		'Crunchy',
		'Fresh',
		'Sweet',
		'Sour',
		'Herby',
		'Pickled',
		'Tahini'
		];

	let topping = [
		'Chilli Oil',
		'Garlic Oil',
		'Brown butter',
		'Sour Cream',
		'Cream',
		'Yoghurt',
		'Feta',
		'Miso Butter',
		'Herb Salsa',
		'Lemon Salsa',
		'Tomato Salsa',
		'Chilli butter',
		'Chilli Salsa',
		'Tahini Dressing',
		'Sumac Onions'
		];

	function generateRecipe() {
		//recipeName = recipeNames[Math.floor(Math.random() * recipeNames.length)];
		// Logic: (10% chance qualifier) (50% chance technique) Veggie + connector +  (10% chance qualifier) (33% chance technique) sideVeggie OR carbs + topping

		// MAIN VEGGIE
		let recipeVeggie = mainVeggie[Math.floor(Math.random() * mainVeggie.length)];		
		//33% chance for Technique
		if (Math.random() < 0.5){
			console.log('OK');
			recipeVeggie =  technique[Math.floor(Math.random() * technique.length)] + ' ' + recipeVeggie;
		}
		//10% chance for Qualifier
		if (Math.random() < 0.2){
			recipeVeggie =  qualifier[Math.floor(Math.random() * qualifier.length)] + ' ' + recipeVeggie;
		}

		let recipeConnector =  connector[Math.floor(Math.random() * connector.length)];

		// SIDE VEGGIE
		let recipeSideVeggie =  sideVeggie[Math.floor(Math.random() * sideVeggie.length)];
		//33% chance for Technique
		if (Math.random() < 0.33){
			recipeSideVeggie =  technique[Math.floor(Math.random() * technique.length)] + ' ' + recipeSideVeggie;
		}
		//10% chance for Qualifier
		if (Math.random() < 0.2){
			recipeSideVeggie =  qualifier[Math.floor(Math.random() * qualifier.length)] + ' ' + recipeSideVeggie;
		}

		// CARBS
		let recipeCarb = carbs[Math.floor(Math.random() * carbs.length)];
		//33% chance for Technique
		if (Math.random() < 0.33){
			recipeCarb =  technique[Math.floor(Math.random() * technique.length)] + ' ' + recipeCarb;
		}
		//10% chance for Qualifier
		if (Math.random() < 0.2){
			recipeCarb =  qualifier[Math.floor(Math.random() * qualifier.length)] + ' ' + recipeCarb;
		}

		let toppingConnect = (recipeConnector == "With") ? 'And' : 'With';
		let recipeTopping =  topping[Math.floor(Math.random() * topping.length)];

		//Final recipe
		if (Math.random() < 0.5){
			recipeName =  recipeVeggie + ' ' + recipeConnector + ' ' +  recipeCarb +  ' ' + toppingConnect + ' ' + recipeTopping;
		}else{
			recipeName =  recipeVeggie + ' ' + recipeConnector + ' ' + recipeSideVeggie + ' ' + toppingConnect + ' ' + recipeTopping;
		}
	}

	generateRecipe(); 

</script>

<svelte:head>
	<title>Ottolenghi Generative Kitchen</title>
	<meta name="description" content="Randomly generated Ottolenghi recipes" />
</svelte:head>

<section>
	<h2>
		{ recipeName }
	</h2>

	<div on:click={ generateRecipe } class="button">Another one!<div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
		max-width: 900px;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}

	h2{
		font-size: 45px;
		font-weight: bold;
		text-transform: uppercase;
		margin-top: 10px;
	}

	.button{
		font-size: 18px;
		background: white;
		font-weight: bold;
		padding: 10px;
		cursor: pointer;
		font-style: italic;
		background-color: white;
		color: #eb533b;
	}


</style>
