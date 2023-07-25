<script lang="ts">
	import { goto } from '$app/navigation';
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

	function handleWindowSizeChange() {
		const screenWidth = window.innerWidth;

		if (screenWidth <= 800) {
			showSkills = true;
			showHobbies = true;
			showEdu = true;
			showAbout = true;
		} 
		
		else {
			showSkills = false;
			showHobbies = false;
			showEdu = false;
			showAbout = true;
		}
	}

	onMount(() => {
		handleWindowSizeChange();
		window.addEventListener('resize', handleWindowSizeChange);
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

	function goHome() {
		goto('/');
	}
</script>

<svelte:head>
	<title>About Me</title>
	<meta name="About Me" content="About" />
	<style type="text/css">
		body {
			font-family: 'Lato', sans-serif;
			background-color: #ffe3f1;
			margin: 0;
			padding: 20px;
		}
	</style>
</svelte:head>

<main>
	<div class="buttonContainer">
		<button on:click={toggleAbout} class="allbtn sectionbtn"><span>About</span></button>
		<button on:click={toggleSkills} class="allbtn sectionbtn"><span>Skills</span></button>
		<button on:click={toggleEdu} class="allbtn sectionbtn"
			><span>Education + Volunteering</span></button
		>
		<button on:click={toggleHobbies} class="allbtn sectionbtn"><span>Hobbies</span></button>
		<button on:click={goHome} class="allbtn homebtn"><span>Home</span></button>
	</div>

	<div class="infoContainer slide-up-fade-in">
		{#if showAbout}
			<div class="aboutContent slide-up-fade-in">
				<p><span>Hi! I'm Katerina and I'm {myAge} years old</span></p>
				<p><span>Currently a 3rd year Computer Science BSc Student at Royal Holloway</span></p>
				<p>
					<span>
						I discovered my passion for computers when I was 11 years old and have been teaching
						myself how to code ever since
					</span>
				</p>
				<p>
					<span>
						I also have a strong affinity for numbers and data, so have recently delved into more
						data based projects
					</span>
				</p>
			</div>
		{/if}

		{#if showSkills}
			<div class="skillsContent slide-up-fade-in">
				<p class="title">Languages</p>
				<ul class="skillsContainer">
					<li>Python</li>
					<li>Java</li>
					<li>SQL</li>
					<li>HTML</li>
					<li>CSS - SCSS</li>
					<li>Prolog</li>
					<li>JavaScript - TypeScript</li>
				</ul>

				<p class="title">Technology</p>
				<ul class="skillsContainer">
					<li>Web Frameworks - React, Svelte, Vite</li>
					<li>Django</li>
					<li>Git</li>
					<li>PostgreSQL</li>
				</ul>

				<p class="title">Other Skills</p>
				<ul class="skillsContainer">
					<li>Linux</li>
					<li>Algorithms & Complexity</li>
					<li>Data Analysis</li>
					<li>Linear Algebra - Multi Dimensional Data Processing</li>
				</ul>
			</div>
		{/if}

		{#if showEdu}
			<div class="educationContent slide-up-fade-in">
				<p class="title">University</p>
				<ul>
					<li>Student Society - Treasurer 2023-2024</li>
					<li>Peer Mentor</li>
				</ul>
				<p class="title">Sixth Form</p>
				<ul>
					<li>Digital Leader</li>
					<li>Robotics Club Leader</li>
					<li>Prefect</li>
				</ul>

				<p class="title">Other Achievements</p>
				<ul>
					<li>Grade 5 Piano - 2016</li>
					<li>Level 3 Algebra Award - 2017</li>
					<li>Brilliant Club 1st in Neuroscience - 2018</li>
					<li>Brilliant Club 1st in Bayesian Statistics - 2019</li>
				</ul>
			</div>
		{/if}

		{#if showHobbies}
			<div class="hobbiesContent slide-up-fade-in">
				<ul>
					<li>Baking</li>
					<li>Playing Piano</li>
					<li>Drawing and Painting</li>
					<li>Sewing and Cross-stitch</li>
					<li>Gaming</li>
					<li>Video Game Modding</li>
				</ul>
			</div>
		{/if}
	</div>
</main>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Baloo+Chettan+2&family=Calligraffitti&display=swap');

	$pink: #f48fb1;
	$purple: #d19ef1;

	::selection {
		background-color: #ffb1ce;
	}

	.slide-up-fade-in {
		animation: slide-up-fade-in ease 1s;
		transform-origin: 50% 50%;
		animation-fill-mode: forwards;

		@keyframes slide-up-fade-in {
			0% {
				opacity: 0;
				transform: translate(0px, 40px);
			}
			100% {
				opacity: 1;
				transform: translate(0px, 0px);
			}
		}
	}

	@mixin cardStyle {
		box-shadow: 0 19px 38px rgba(0, 0, 0, 0.3), 0 12px 9px rgba(0, 0, 0, 0.22);
		display: table;
		flex-direction: column;
		align-items: center;
		margin: auto;
		border-radius: 2rem;
		width: 50%;
		height: 50%;
		background-color: rgba(255, 90, 151, 0.1);
		max-width: 65%;
	}

	@mixin listStyle {
		ul {
			display: flex;
			flex-wrap: wrap;
			align-content: center;
			padding: 0;

			li {
				list-style-type: none;
				display: inline;
				float: none;
				background-color: rgba(255, 255, 255, 0.5);
				fill-opacity: 0.2;
				border-radius: 1rem;
				padding: 1% 3%;
				margin: 2%;
			}
		}
	}

	.hobbiesContent {
		@include cardStyle;
		@include listStyle;
	}

	.skillsContent,
	.educationContent {
		@include cardStyle;
		@include listStyle;

		p {
			font-weight: bold;
			margin: 3%;
		}
	}

	.buttonContainer {
		display: flex;
		justify-content: center;
		gap: 10px;
		margin: 30px 0;
	}

	.allbtn {
		width: auto;
		height: 40px;
		color: #fff;
		border-radius: 5px;
		padding: 10px 30px;
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

	@mixin buttonNoColour {
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

		span:before,
		span:after {
			position: absolute;
			content: '';
			left: 0;
			top: 0;
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

	.sectionbtn {
		@include buttonNoColour;
		background-image: linear-gradient(315deg, #f8bbd0 0%, $pink 74%);

		&:before,
		&:after {
			background: $pink;
		}

		span:hover {
			color: $pink;
		}

		span:before,
		span:after {
			background: $pink;
		}
	}

	.homebtn {
		@include buttonNoColour;
		background-image: linear-gradient(315deg, rgb(235, 204, 255) 0%, rgb(209, 158, 241) 74%);

		&:before,
		&:after {
			background: $purple;
		}

		span:hover {
			color: $purple;
		}

		span:before,
		span:after {
			background: $purple;
		}
	}

	.title {
		font-family: 'Calligraffitti', cursive;
		font-weight: 700;
		font-size: 1.5rem;
		transform: translate(-1%, -1%);
		letter-spacing: 0.02em;
		color: #ef5097;
		text-shadow: 2px 2px 2px #00000048;
	}

	.aboutContent {
		@include cardStyle;

		p {
			text-align: center;
			padding: 2%;

			span {
				padding: 1%;
				background-color: rgba(255, 255, 255, 0.5);
				border-radius: 10px;
			}
		}
	}

	@media (max-width: 800px) {
		.sectionbtn {
			display: none;
		}

		.infoContainer {
			display: flex;
			flex-direction: column;
			gap: 50px;
			justify-content: center;
		}

		.skillsContent,
		.hobbiesContent,
		.educationContent,
		.aboutContent {
			box-shadow: 0 10px 20px rgba(133, 133, 133, 0.3), 0 10px 6px rgba(133, 133, 133, 0.3);
			width: 100%;
			max-width: 100%;
		}
	}
</style>
