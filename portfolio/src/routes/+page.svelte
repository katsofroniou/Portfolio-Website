<script>
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
	<style type="text/css">
		body {
			--primary-rgb: rgb(255, 118, 164);
			background-color: rgb(255, 227, 241);
		}
	</style>
</svelte:head>

<main>
	<section>
		<div class="screen">
			<div class="screen-img" />
			<div class="screen-overlay" />
			<div class="screen-content">
				<div class="screen-user">
					<span class="content" data-value="ABOUT">
						<a href="/about">ABOUT</a>
					</span>
				</div>
			</div>
		</div>
		<div class="screen">
			<div class="screen-img" />
			<div class="screen-overlay" />
			<div class="screen-content">
				<div class="screen-user">
					<span class="content" data-value="CONTACTS">
						<div class="social">
							<a href="https://github.com/katsofroniou/">GITHUB</a>
							<a href="https://www.linkedin.com/in/katerina-sofroniou-319aba244/">LINKEDIN</a>
							<a href="/contact">CONTACT ME</a>
						</div>
					</span>
				</div>
			</div>
		</div>
		<div class="screen">
			<div class="screen-img" />
			<div class="screen-overlay" />
			<div class="screen-content">
				<div class="screen-user">
					<span class="content" data-value="PROJECTS">
						<a href="/projects">PROJECTS</a>
					</span>
				</div>
			</div>
		</div>
	</section>
</main>

<style>
	.social {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		height: 100%;
	}

	.social a {
		margin: 1rem 0;
	}

	@keyframes pan-image {
		0% {
			background-position: 30% 35%;
			background-size: 350%;
		}
		10% {
			background-position: 32% 37%;
			background-size: 350%;
		}
		20% {
			background-position: 35.000001% 40%;
			background-size: 350%;
		}
		30% {
			background-position: 38% 43%;
			background-size: 350%;
		}
		40% {
			background-position: 41% 46%;
			background-size: 350%;
		}
		50% {
			background-position: 45% 50%;
			background-size: 350%;
		}
		60% {
			background-position: 49% 54%;
			background-size: 350%;
		}
		70% {
			background-position: 53% 58%;
			background-size: 350%;
		}
		80% {
			background-position: 57% 62%;
			background-size: 350%;
		}
		90% {
			background-position: 62% 67%;
			background-size: 350%;
		}
		100% {
			background-position: 66% 71%;
			background-size: 350%;
		}
	}

	section {
		border: none;
		display: flex;
		gap: 1rem;
		background-size: auto;
	}

	main {
		margin: 0;
		padding: 0;
	}

	.screen > .screen-content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-end;
		flex-grow: 1;
		gap: 4rem;
		position: relative;
		z-index: 3;
		margin: 1rem;
		padding-bottom: 3%;
	}

	.screen {
		width: calc(25%);
		margin-bottom: 2rem;
		display: flex;
		aspect-ratio: 10 / 16;
		overflow: hidden;
		position: relative;
		z-index: 10;
		border-radius: 1rem;
		box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
	}

	.screen::before {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-size: cover;
		opacity: 0.6;
		animation: 15s linear 0s infinite alternate pan-image;
	}

	.screen:nth-child(1)::before {
		background-image: url('https://images.unsplash.com/photo-1616285720779-9e597265df0c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=659&q=80');
	}

	.screen:nth-child(2)::before {
		background-image: url('https://images.unsplash.com/photo-1463043254199-7a3efd782ad1?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80');
	}

	.screen:nth-child(3)::before {
		background-image: url('https://images.unsplash.com/photo-1587421976536-c2de1cac8bb3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80');
	}

	.content a {
		text-align: center;
	}

	.screen-user {
		position: absolute;
		display: flex;
		top: 25%;
		justify-content: center;
		align-items: center;
		height: 100%;
	}

	.screen-user a {
		color: rgb(184, 12, 118);
		text-decoration: none;
		font-size: 2rem;
	}

	@media only screen and (min-width: 768px) {
		/* Styles for tablet and desktop */
		section {
			display: flex;
			flex-wrap: wrap;
			align-items: center;
			justify-content: center;
			height: 95vh;
			padding: 0 2rem;
		}
	}

	@media screen and (max-width: 767px) {
		section {
			flex-direction: column;
			align-items: center;
		}

		* {
			box-sizing: border-box;
			padding-top: 25%;
		}

		.screen {
			width: 75%;
		}
	}
</style>
