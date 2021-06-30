<script>
	import Navbar from "./components/Navbar.svelte";
	import Player from "./components/Player.svelte";
	import AddPlayer from "./components/AddPlayer.svelte"
	

	 let players = [

		 {name: "Pera Perić", points: 20},
		 {name: "Žika Žigić", points: 32},
		 {name: "Ivan Marković", points: 51},
	 ]
	 
	 const addNewPlayer = e => {
		 let newPlayer = e.detail;
		 players = [...players, newPlayer];
	 }

</script>

<div>
	<Navbar/>
</div>

<div class="list-container">

	<AddPlayer  on:addplayer={addNewPlayer}/>

	{#if players.length === 0}
		<p>There are no players</p>
	{:else}
		{#each players as player} 
			<Player name={player.name} points={player.points}/>
		{/each}
	{/if}

</div>

<style>

	.list-container {
		max-width: 600px;
		margin: auto;
		display: flex;
		flex-direction: column;
		gap: .5rem;
		padding-top: 1rem;
	}

</style>