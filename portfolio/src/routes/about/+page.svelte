<script lang="ts">
	const dob = new Date(2002, 8, 23);
	const now = new Date(Date.now());

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

	const myAge: number = age(dob, now);
</script>

<svelte:head>
	<title>About Me</title>
	<meta name="About Me" content="About" />
	<style type="text/css">
		body {
			font-family: Arial, sans-serif;
			background-color: #ffe3f1;
			margin: 0;
			padding: 20px;
		}
	</style>
</svelte:head>

<main>
	<div class="name-age">
		<p class="name">Katerina Sofroniou, {myAge}</p>
	</div>
	<div class="section-container">
		<div class="section">
			<div class="content">
				<h3>Education and Volunteering</h3>
				<div class="subsection">
					<h5 class="subtitle">Education</h5>
					<ul>
						<li>Royal Holloway 2021-2024</li>
						<li>Computer Science BSc</li>
					</ul>
				</div>
				<div class="subsection">
					<h5 class="subtitle">Volunteering</h5>
					<p>University</p>
					<ul>
						<li>Anime and Manga Society - Diversity and Inclusivity Rep 2023-2023</li>
						<li>Anime and Manga Society - Treasurer 2023-2024</li>
						<li>Peer Mentor</li>
					</ul>
					<p>Secondary School</p>
					<ul>
						<li>Digital Leader</li>
						<li>Robotics Club Volunteer</li>
						<li>Prefect</li>
					</ul>
				</div>
				<div class="subsection">
					<h5 class="subtitle">Other Achievements</h5>
					<ul>
						<li>Grade 3 Piano - 2016</li>
						<li>Level 3 Algebra Award - 2017</li>
						<li>Brilliant Club 1st in Neuroscience - 2018</li>
						<li>Brilliant Club 1st in Bayesian Statistics - 2019</li>
					</ul>
				</div>
			</div>

			<div class="section">
				<div class="content">
					<h3>Skills</h3>
					<div class="subsection">
						<h5 class="subtitle">Languages</h5>
						<ul class="skills-container">
							<li class="skill-item">Python</li>
							<li class="skill-item">Java</li>
							<li class="skill-item">SQL</li>
							<li class="skill-item">HTML - CSS</li>
							<li class="skill-item">JavaScript - TypeScript</li>
							<li class="skill-item">Prolog</li>
						</ul>
					</div>
					<div class="subsection">
						<h5 class="subtitle">Technology</h5>
						<ul class="skills-container">
							<li class="skill-item">Web Frameworks - React, Svelte, Vite</li>
							<li class="skill-item">Django</li>
							<li class="skill-item">Git</li>
							<li class="skill-item">PostgreSQL</li>
						</ul>
					</div>
					<div class="subsection">
						<h5 class="subtitle">Other Skills</h5>
						<ul class="skills-container">
							<li class="skill-item">Linux</li>
							<li class="skill-item">Linear Algebra - Multi Dimensional Data Processing</li>
							<li class="skill-item">Algorithms & Complexity</li>
							<li class="skill-item">Data Analysis</li>
						</ul>
					</div>
				</div>
			</div>

			<div class="section">
				<div class="content">
					<h3>Hobbies</h3>
					<ul class="hobbies-container">
						<li class="hobby-item">Gaming</li>
						<li class="hobby-item">Painting and Drawing</li>
						<li class="hobby-item">Playing Piano</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</main>

<style>

</style>
