<script lang='ts'>
	const dob = new Date(2002, 08, 23);
	const now = new Date(Date.now())

	function age(dob: Date, now: Date) {
		const yearsDiff = now.getFullYear() - dob.getFullYear();
		const monthsDiff = now.getMonth() - dob.getMonth();
		const daysDiff = now.getDate() - dob.getDate();

		let age = yearsDiff;

		if (monthsDiff < 0 || (monthsDiff === 0 && daysDiff < 0)) {
			age--;
		} 

		return age;
	}

	const myAge:number = age(dob, now);
</script>

<svelte:head>
	<title>About Me</title>
	<meta name="About Me" content="About" />
	<style type="text/css">
		body {
			background-color: rgb(255, 227, 241);
		}
	</style>
</svelte:head>

<main>
	<h1>About Me</h1>

	<p class="name">Katerina Sofroniou</p>
	<p class="dob">{myAge}</p>
</main>

<style>
</style>