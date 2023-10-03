<script>
	import Modal from './Modal05.svelte';
  
	let showModal = false;
  
	let toggleModal = () => {
	  showModal = !showModal;
	};
  
	let people = [
    { name: 'Geto', beltColour: 'black', age: 25, id: 1 },
    { name: 'Gojo', beltColour: 'orange', age: 45, id: 2 },
    { name: 'Shoko', beltColour: 'brown', age: 35, id: 3 }
   ];
  
	const handleClick = (e, id) => {
	  people = people.filter(person => person.id != id);
	  console.log(e);
	};
  </script>
  
  <Modal message='Hello, human!' {showModal} on:click={toggleModal} />
  <main>
	<button on:click|once={toggleModal}>Open Modal</button>
	{#each people as person (person.id)}
	  <div>
		<h4>{person.name}</h4>
		{#if person.beltColour === 'black'}
		  <p><strong>jjk
		  </strong></p>
		{/if}
		<p>{person.age} years old, {person.beltColour} belt.</p>
		<button on:click={(e) => handleClick(e, person.id)}>delete</button>
	  </div>
	{:else}
	  <p>There are no people to show...</p>
	{/each}
  </main>
  
  <style>
	  main {
		  text-align: center;
		  padding: 1em;
		  max-width: 240px;
		  margin: 0 auto;
	  }
  
	  @media (min-width: 640px) {
		  main {
			  max-width: none;
		  }
	  }
  </style>