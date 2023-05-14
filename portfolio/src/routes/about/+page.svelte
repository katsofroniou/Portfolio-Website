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

	<div class="name-age">
		<p class="name">Katerina Sofroniou, {myAge}</p>
	</div>

	<div class="edu-vol">
		<h3>Education and Volunteering</h3>
		
		<h5>Education</h5>
		<ul>
			<li>Royal Holloway 2021-2024</li>
			<li>Computer Science Bsc</li>
		</ul>
		
		<h5>Volunteering</h5>
		<p> University </p>
		<ul>
			<li>Anime and Manga Society - Diversity and Inclusivity Rep 2023-2023</li>
			<li>Anime and Manga Society - Treasurer 2023-2024</li>
			<li>Peer Mentor</li>
		</ul>

		<p> Secondary School </p>
		<ul>
			<li>Digital Leader</li>
			<li>Robotics Club Volunteer</li>
			<li>Prefect</li>
		</ul>

		<h5>Other Achievements</h5>
		<ul>
			<li>Grade 3 Piano - 2016</li>
			<li>Level 3 Algebra Award - 2017</li>
			<li>Brilliant Club 1st in Neuroscience - 2018</li>
			<li>Brilliant Club 1st in Bayesian Statistics - 2019</li> 
		</ul>
	</div>

	<div class="skills">
		<h3>Skills</h3>
		<h5>Languages</h5>
		<ul>
			<li>Python</li>
			<li>Java</li>
			<li>SQL</li>
			<li>HTML - CSS - Javascript - Typescript</li>
			<li>Prolog</li>
		</ul>
		<h5>Technology</h5>
		<ul>
			<li>Web Frameworks - React, Svelte, Vite</li>
			<li>Django</li>
			<li>Git</li>
			<li>PostgreSQL</li>
		</ul>
		<h5>Other Skills</h5>
		<ul>
			<li>Linux</li>
			<li>Linear Algebra - Multi Dimensional Data Processing</li>
			<li>Algorithms & Complexity</li>
			<li>Data Analysis</li>
		</ul>
	</div>

	<div class="hobbies">
		<h3>Hobbies</h3>
		<ul>
			<li>Gaming</li>
			<li>Painting and Drawing</li>
			<li>Playing Piano</li>
		</ul>
	</div>
</main>

<style>
</style>