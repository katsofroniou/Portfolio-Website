<script lang="ts">
	import { goto } from '$app/navigation';

	function goHome() {
		goto('/');
	}
</script>

<svelte:head>
	<title>Kat's Projects</title>
	<meta name="Kat's Projects" content="A collection of all projects" />
	<style type="text/css">
		body {
			font-family: 'Lato', sans-serif;
			background-color: #ffe3f1;
			align-items: center;
			display: flex;
			height: 100vh;
			justify-content: center;
			margin: 0px;
			overflow: hidden;
			padding: 0px;
		}
	</style>
</svelte:head>

<main>
	<div class="titleContainer">
		<h1 class="title">My Projects</h1>
	</div>
	<div class="buttonContainer">
		<button on:click={goHome} class="allbtn homebtn"><span>Home</span></button>
	</div>
	<div id="projectsContainer">
		<div class="project">
			<a href="https://github.com/katsofroniou/london-fire" target="_blank">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>London Fire Department Data Analysis</h3>
							<p>
								My first web scraping and data project! I was really excited to start this and hope
								to do more with it in the future
							</p>
						</div>
					</div>
				</div>
			</div>
		</a>
		</div>
		<div class="project">
			<a href="https://github.com/katsofroniou/RHUL-Robotic-Rubiks-Cube-Solver" target="_blank">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>RHUL Robotic Rubiks Cube Solver</h3>
							<p>
								Created for my first year group project at university. It is a small lego Ev3 robot
								that can solve a Rubik's cube by scanning each side and calculating the correct
								moved
							</p>
						</div>
					</div>
				</div>
			</div>
		</a>
		</div>
		<div class="project">
			<a href="https://github.com/katsofroniou/CityUOL-Java-Bootcamp" target="_blank">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>City UOL Java Bootcamp MP3 Player</h3>
							<p>
								After learning Java for 2 weeks through Processing, I created a small MP3 music
								player with visual representation of the music currently playing
							</p>
						</div>
					</div>
				</div>
			</div>
			</a>
		</div>
		<div class="project">
			<a href="https://github.com/katsofroniou/CityUOL-Discord-bot" target="_blank">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>City UOL Discord Bot</h3>
							<p>
								A small helper bot for the City UOL server for students. It was created to allow
								easy access to regularly needed information such as class schedules, coursework due
								dates and Zoom room codes and passwords
							</p>
						</div>
					</div>
				</div>
			</div>
			</a>
		</div>
		<div class="project">
			<a href="https://github.com/katsofroniou/Portfolio-Website" target="_blank">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Portfolio Website</h3>
							<p>
								This source code for this website! It was created using Svelte, Vite, TypeScript and
								SCSS. It was the first time I used each of these languages/technologies, so it was a
								bit of a challenge but worked out well :D
							</p>
						</div>
					</div>
				</div>
			</div>
			</a>
		</div>
		<div class="project">
			<div class="content">
				<div class="infoContainer">
					<div class="info">
						<div class="title">
							<h3>Future Projects</h3>
							<p>
								I have many more projects in development that I plan to complete over the summer of
								2023; I'm looking forward to sharing them!
							</p>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</main>

<style lang="scss">
	$purple: #d19ef1;
	main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	a {
		text-decoration: none;
	}

	.titleContainer {
		width: 100%;
		display: flex;
		justify-content: center;

		h1 {
			color: mix(#fff, #ff0055, 85%);
			font-size: calc(1em + 7vh);
			font-weight: 900;
			text-shadow: -0.0075em 0.0075em 0 mix(#fff, #e91e63, 94%),
				0.005em 0.005em 0 mix(#fff, #e91e63, 60%), 0.01em 0.01em 0 mix(#fff, #e91e63, 62%),
				0.015em 0.015em mix(#fff, #e91e63, 64%), 0.02em 0.02em 0 mix(#fff, #e91e63, 66%),
				0.025em 0.025em 0 mix(#fff, #e91e63, 68%), 0.03em 0.03em 0 mix(#fff, #e91e63, 70%),
				0.035em 0.035em 0 mix(#fff, #e91e63, 72%);
		}
	}
	#projectsContainer {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		position: relative;
		gap: 10px;
		max-width: 1000px;
		width: calc(100% - 20px);
	}

	.project {
		flex: 0 0 calc(33.33% - 20px);
		height: 200px;
		background-color: #f5f5f5;
		margin-bottom: 20px;
		border-radius: 15px;
		box-shadow: 0 10px 19px rgba(0, 0, 0, 0.3), 0 6px 4.5px rgba(0, 0, 0, 0.22);
		overflow: hidden;
		transition: transform 0.25s ease-out;

		&:hover {
			transform: translateY(2px);
			transition: transform 0.25s ease-in-out;
		}

		.content {
			padding: 20px;

			.infoContainer {
				display: flex;
				align-items: center;

				.info {
					flex: 1;

					.title {
						h3 {
							font-size: 18px;
							margin-bottom: 10px;
							color: mix(#fff, #ff0055, 50%);
						}

						p {
							font-size: 14px;
							color: #888;
						}
					}
				}
			}
		}
	}

	/* Separate for extra button styles later on */
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
</style>
