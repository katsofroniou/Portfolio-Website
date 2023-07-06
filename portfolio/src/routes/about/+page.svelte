<script lang="ts">
	import { onMount } from 'svelte';

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

	let showSkills = false;
	let showHobbies = false;
	let showEdu = false;
	let showAbout = false;

	onMount(() => {
		showSkills = true;
	});

	function toggleSkills() {
		showSkills = true;
		showHobbies = false;
		showEdu = false;
		showAbout = false;
	}

	function toggleHobbies() {
		showSkills = false;
		showHobbies = true;
		showEdu = false;
		showAbout = false;
	}

	function toggleEdu() {
		showSkills = false;
		showHobbies = false;
		showAbout = false;
		showEdu = true;
	}

	function toggleAbout() {
		showSkills = false;
		showHobbies = false;
		showEdu = false;
		showAbout = true;
	}
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
	<div class="buttonContainer">
		<button on:click={toggleEdu} class="allbtn sectionbtn"
			><span>Education + Volunteering</span></button
		>
		<button on:click={toggleSkills} class="allbtn sectionbtn"><span>Skills</span></button>
		<button on:click={toggleHobbies} class="allbtn sectionbtn"><span>Hobbies</span></button>
		<button on:click={toggleAbout} class="allbtn sectionbtn"><span>About</span></button>
	</div>

	{#if showSkills}
		<div class="skillsContent">
			<p>Languages</p>
			<ul class="skillsContainer">
				<li>Python</li>
				<li>Java</li>
				<li>SQL</li>
				<li>HTML</li>
				<li>CSS - SCSS</li>
				<li>Prolog</li>
				<li>JavaScript - TypeScript</li>
			</ul>

			<p>Technology</p>
			<ul class="skillsContainer">
				<li>Web Frameworks - React, Svelte, Vite</li>
				<li>Django</li>
				<li>Git</li>
				<li>PostgreSQL</li>
			</ul>

			<p>Other Skills</p>
			<ul class="skillsContainer">
				<li>Linux</li>
				<li>Linear Algebra - Multi Dimensional Data Processing</li>
				<li>Algorithms & Complexity</li>
				<li>Data Analysis</li>
			</ul>
		</div>
	{/if}

	{#if showHobbies}
		<div class="hobbiesContent">
			<ul>
				<li>Baking</li>
				<li>Playing Piano</li>
				<li>Drawing and Painting</li>
				<li>Sewing and Cross-stitch</li>
			</ul>
		</div>
	{/if}

	{#if showEdu}
		<div class="educationContent">
			<p>University</p>
			<ul>
				<li>Student Society - Treasurer 2023-2024</li>
				<li>Peer Mentor</li>
			</ul>
			<p>Secondary School</p>
			<ul>
				<li>Digital Leader</li>
				<li>Robotics Club Volunteer</li>
				<li>Prefect</li>
			</ul>

			<p>Other Achievements</p>
			<ul>
				<li>Grade 5 Piano - 2016</li>
				<li>Level 3 Algebra Award - 2017</li>
				<li>Brilliant Club 1st in Neuroscience - 2018</li>
				<li>Brilliant Club 1st in Bayesian Statistics - 2019</li>
			</ul>
		</div>
	{/if}

	{#if showAbout}
		<div class="aboutContent">
			<p>about me - {myAge}</p>
		</div>
	{/if}
</main>

<style lang="scss">
	$pink: #f48fb1;
	$white: #fff;
	$background: #f0ecfc;

    .skillsContent {
		display: table;
		flex-direction: column;
		align-items: center;
		margin: auto;
		width: 50%;
		height: 50%;
		background-color: $background;

        p {
            font-weight: bold;
            margin: 3%;
        }

		ul {
            display: flex;
            flex-wrap: wrap;
            align-content: center;
			padding: 0;

			li {
				list-style-type: none;
                display: inline;
                float: none;
				background-color: $white;
				fill-opacity: 0.2;
				border-radius: 1rem;
				padding: 1% 3%;
				margin: 2%;
			}
		}
	}

    
    .buttonContainer {
		display: flex;
		justify-content: center;
		gap: 10px;
		margin-bottom: 20px;
	}

	.allbtn {
		width: auto;
		height: 40px;
		color: $white;
		border-radius: 5px;
		padding: 10px 30px;
		font-family: 'Lato', sans-serif;
		font-weight: 500;
		background: transparent;
		cursor: pointer;
		transition: all 0.3s ease;
		position: relative;
		display: inline-block;
		box-shadow: inset 2px 2px 2px 0px rgba(255, 255, 255, 0.5), 7px 7px 20px 0px rgba(0, 0, 0, 0.1),
			4px 4px 5px 0px rgba(0, 0, 0, 0.1);
		outline: none;
		min-width: 10rem;
	}

	.sectionbtn {
		background-color: $background;
		background-image: linear-gradient(315deg, #f8bbd0 0%, $pink 74%);
		line-height: 42px;
		padding: 0;
		border: none;

		span {
			position: relative;
			display: block;
			width: 100%;
			height: 100%;
		}

		&:before,
		&:after {
			position: absolute;
			content: '';
			right: 0;
			bottom: 0;
			background: $pink;
			transition: all 0.3s ease;
		}

		&:before {
			height: 0%;
			width: 2px;
		}

		&:after {
			width: 0%;
			height: 2px;
		}

		&:hover:before {
			height: 100%;
		}

		&:hover:after {
			width: 100%;
		}

		&:hover {
			background: transparent;
		}

		span:hover {
			color: $pink;
		}

		span:before,
		span:after {
			position: absolute;
			content: '';
			left: 0;
			top: 0;
			background: $pink;
			transition: all 0.3s ease;
		}

		span:before {
			width: 2px;
			height: 0%;
		}

		span:after {
			height: 2px;
			width: 0%;
		}

		span:hover:before {
			height: 100%;
		}

		span:hover:after {
			width: 100%;
		}

		&:active {
			transform: translateY(2px);
		}
	}
</style>
