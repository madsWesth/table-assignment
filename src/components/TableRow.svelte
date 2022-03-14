<script>
    export let person;
</script>

<tr>
    {#each Object.keys(person) as key}
        {#if key.toString() != "avatar"}
            <td>{person[key]}</td>
        {:else if key.toString() === "avatar"}
            <td><img src="{person[key]}" alt=""></td>
        {/if}
    {/each}
</tr>

<style>
    tr, td {
        border: 2px solid #ff3e00;
    }
</style>