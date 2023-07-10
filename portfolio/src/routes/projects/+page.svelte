<script lang="ts">
	import { onMount } from 'svelte';

	onMount(() => {
		const handleMouseMove = (e: MouseEvent) => {
			const projects = document.getElementsByClassName('project') as HTMLCollectionOf<HTMLElement>;
			for (const project of projects) {
				const rect = project.getBoundingClientRect();
				const x = e.clientX - rect.left;
				const y = e.clientY - rect.top;

				project.style.setProperty('--mouse-x', `${x}px`);
				project.style.setProperty('--mouse-y', `${y}px`);
			}
		};

		const projectsContainer = document.getElementById('projectsContainer');
		if (projectsContainer) {
			projectsContainer.addEventListener('mousemove', handleMouseMove);
		}

		return () => {
			if (projectsContainer) {
				projectsContainer.removeEventListener('mousemove', handleMouseMove);
			}
		};
	});
</script>

<svelte:head>
	<title>Kat's Projects</title>
	<meta name="Kat's Projects" content="A collection of all projects" />
	<style type="text/css">
		body {
			background-color: #ffe3f1;
			display: flex;
			justify-content: center;
			overflow: hidden;
		}
	</style>
</svelte:head>

<main>
	<div id="projectsContainer">
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Project 1</h3>
							<p>info about project</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Project 2</h3>
							<p>info about project</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Project 3</h3>
							<p>info about project</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Project 4</h3>
							<p>info about project</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Project 5</h3>
							<p>info about project</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Project 6</h3>
							<p>info about project</p>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</main>

<style lang="scss">
	$test: rgba(197, 138, 197, 0.8);
	
	main {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	#projectsContainer {
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
		max-width: 1000px;
		justify-content: center;

		&:hover > .project::after {
			opacity: 1;
		}
	}

	.project {
		background-color: rgba(255, 136, 255, 0.534);
		border-radius: 10px;
		cursor: pointer;
		display: flex;
		flex-direction: row;
		height: 260px;
		position: relative;
		width: 300px;

		&:hover::before {
			opacity: 1;
		}

		&::before,
		&::after {
			content: '';
			border-radius: inherit;
			position: absolute;
			height: 100%;
			width: 100%;
			top: 0px;
			left: 0px;
			opacity: 0;
			transition: opacity 500ms;
		}

		&::before {
			background: radial-gradient(
				800px circle at var(--mouse-x) var(--mouse-y),
				rgba(255, 255, 255, 0.4),
				transparent 40%
			);
			z-index: 3;
		}

		.content {
			background-color: rgba(197, 104, 197, 0.534);
			background-size: 400% 400%;
			animation: gradientAnimation 10s ease infinite;
			border-radius: inherit;
			display: flex;
			flex-direction: column;
			flex-grow: 1;
			inset: 1px;
			padding: 10px;
			position: absolute;
			z-index: 2;
		}

		@keyframes gradientAnimation {
			0% {
				background-position: 0% 50%;
			}
			50% {
				background-position: 100% 50%;
			}
			100% {
				background-position: 0% 50%;
			}
		}
	}

	.infoContainer {
		align-items: center;
		display: flex;
		flex-grow: 1;
		justify-content: flex-start;
		padding: 0, 20px;
	}

	.info {
		align-items: flex-start;
		display: flex;
		gap: 10px;
	}
</style>
