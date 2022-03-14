<script>
    export let headers
    import { createEventDispatcher } from "svelte"
    const dispatch = createEventDispatcher()


    function sort(event){
        dispatch('sort', {
            header: event.target.innerText
        })
    }
</script>

<tr>
    {#each headers as column}
        <th on:click={sort}>{column}</th>
    {/each}
</tr>

<style>

</style>