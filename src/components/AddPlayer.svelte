<script>
import { createEventDispatcher } from "svelte"

    const dispatch = createEventDispatcher();

    let player = {
        name: "",
        points: 0,
    }

    const onSubmit = e => {
        e.preventDefault();
        dispatch("addplayer", player);
        player = {
            name: "",
            points: 0,
        }
    }
</script>

<form class="new-player-form" on:submit={onSubmit}>
    <input type="text" placeholder="Enter player name" bind:value={player.name}/>
    <input type="number" placeholder="Enter player points" bind:value={player.points}/>
    <input type="submit" value="Add player"/>
</form>

<style>

    .new-player-form {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: .5rem;
    }

</style>