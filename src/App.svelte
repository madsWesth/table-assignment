<script>
	import { faker } from "@faker-js/faker";
	import PeopleTable from "./components/PeopleTable.svelte"

	let people = generatePeople(25)

	function generatePeople(numberOfPeople) {
		const peopleArray = []
		for (let i = 0; i < numberOfPeople; i++) {
			peopleArray.push({
				firstName: faker.name.firstName(),
				lastName: faker.name.firstName(),
				jobTitle: faker.name.jobTitle(),
				jobArea: faker.name.jobArea(),
				avatar: faker.image.avatar()})
		}
		return peopleArray
	}

</script>

<main>
	<h1>People table</h1>
	<p>I put in effort to make sure that adding more info about a person would dynamically make new cloumns, table can be sorted if you click the column name</p>
<div>
	<div>
		<PeopleTable people={people}/>
	</div>
</div>

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

	div {
		display: flex;
		justify-content: center;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>