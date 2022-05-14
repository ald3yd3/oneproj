<script>
	import Modal from './modal.svelte'
	let people = [
		{name: 'yoshi', belcolor:'black', age:25, id:1},
		{name: 'jon', belcolor:'blue', age:30, id:2},
		{name: 'abhinav', belcolor:'rainbow', age:19, id:3}
	];
	const handleclick = (id) => {
		 people = people.filter( (person) => person.id != id )
	}
let num =6;	
</script>
<Modal/>
<main>
{#each people as person (person.id)}
<div>
	<h4>{person.name}</h4>
	{#if person.belcolor==='black'} <p><strong>master ninja</strong></p> {/if}
	<p>{person.age} years old, {person.belcolor} belt. </p>
	<button on:click={() =>  handleclick(person.id)}>delete entry</button>

</div>	
{:else} <p>there are no people to show...</p>
{/each}

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>