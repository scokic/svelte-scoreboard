<script>
    export let name;
	export let points;
	let showControls = false;

    const addPoint = () => points += 1;
	const removePoint = () => points -= 1;
	const toggleControls = () => showControls = !showControls;
</script>

<div class="card">
    <h1>{name}</h1>
    <h3>Points: {points}</h3>
    <button class="btn toggle-btn" on:click={toggleControls}>{#if showControls}-{:else}+{/if}</button>

    {#if showControls}
        <button class="btn" on:click={addPoint} >+1</button>
        <button class="btn btn-dark" on:click={removePoint}>-1</button>
        <input type="number" bind:value={points}>
    {/if}
</div>

<style>

.card {
	border: 1px solid lightgrey;
	padding: 1rem 2rem;
	border-radius: .25rem;
	position: relative;
}


.btn {
	padding: .5rem 1rem;
	background-color: white;
	color: black;
	border: 1px solid lightgrey;
	cursor: pointer;
}

.btn-dark {
	background-color: black;
	color:white;
}

.toggle-btn {
	position: absolute;
	top: 1rem;
	right: 1rem;
}

</style>