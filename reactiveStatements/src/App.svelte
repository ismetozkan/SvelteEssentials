<script>
	let value = 0;
	let limit;  // Bound with Input

	//If the value in it is refreshed, it is triggered again.
	//Thanks to this expression :) --> ' $: '
	$: if(limit === value){
		const hr = document.querySelector('hr')
		hr.append('You have reached the number' +
				' that will trigger the if condition') ;
	}

	/*
	// Try without ' $: ' expression
	if(limit === value){
		const hr = document.querySelector('hr')
		hr.append('You have reached the number' +
				' that will trigger the if condition') ;
	}
	*/

	function increase() {
		value++ ;

		const h1 = document.querySelector("h1");
		h1.innerText = `${value}`;
	}

	function counter () {
		const h1 = document.querySelector("h1");
		h1.innerText = `${value}`;

	}

	function initial() {
		const h1 = document.querySelector("h1");
		h1.innerText = `VALUE`;
	}


	$: console.log(value);
</script>

<main>
	<label>
		<input type=range bind:value={limit} min={1} max={15} step={1}><br>
		{#if limit}
		{limit}
		{:else}
		^____move____^
		{/if}
	</label>

	<h1>VALUE</h1>
	<button on:mouseleave={initial}
			on:mouseenter={counter}
			on:click={increase}>Enter Area and Click to Raise</button>
	<hr>
	<hr>

</main>

<!--
///////////-STYLE-STYLE-STYLE//////////////////////////////////////////////
///////////////////////-STYLE-STYLE-STYLE-STYLE-STYLE-STYLE////////////////
-STYLE-STYLE-STYLE-STYLE-STYLE-STYLE///////////////////////////////////////
//////////////////////////////-STYLE-STYLE-STYLE-STYLE-STYLE///////////////
-->

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		width: 300px;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		border: solid black 1px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>