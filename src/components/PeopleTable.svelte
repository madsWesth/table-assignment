<script>
    import TableHead from "./TableHead.svelte";
    import TableRow from "./TableRow.svelte";

    export let people;

    function sortByHeader(event){
        const header = event.detail.header
        people = people.sort((a, b) => {
            if (a[header] > b[header]) {
                return 1
            } else if (a[header] < b[header]){
                return -1
            }
            return 0
        })
    }
</script>

<table>
    <TableHead on:sort={sortByHeader} headers={Object.keys(people[0])} />
    {#each people as person}
        <TableRow {person} />
    {/each}
</table>

<style>
    table {
        border-collapse: collapse;
        width: 1000px;
    }
</style>
