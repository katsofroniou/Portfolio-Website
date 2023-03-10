<script>
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section style="display: flex; gap: 1rem;">
	<div class="screen">
		<div class="screen-img" />
		<div class="screen-overlay" />
		<div class="screen-content">
			<div class="screen-user">
				<span class="about" data-value="ABOUT">
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
				<span class="about" data-value="ABOUT">
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
				<span class="about" data-value="ABOUT">
					<a href="/about">ABOUT</a>
				</span>
			</div>
		</div>
	</div>
</section>

<style>
	.screen {
		width: 500px;
		display: flex;
		border: 3px solid rgba(var(--primary-rgb), 0.8);
		aspect-ratio: 10 / 16;
		border-radius: 1rem;
		background-color: rgba(var(--primary-rgb), 0.15);
		overflow: hidden;
		position: relative;
		z-index: 10;
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

	.screen > .screen-img {
		background-image: url("https://images.unsplash.com/photo-1463043254199-7a3efd782ad1?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1169&q=80");
		height: 100%;
		width: 100%;
		position: absolute;
		z-index: 1;
		left: 0px;
		top: 0px;
		background-size: 300%;
		background-position: 0% 0%;
		opacity: 0.6;
		animation: pan-image 15s linear infinite;
	}

	@media only screen and (min-width: 768px) {
		/* Styles for tablet and desktop */
		section {
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
			padding: 0 2rem;
		}

		.screen {
			width: calc(33.33% - 2rem);
			margin-bottom: 2rem;
		}
	}

	@media screen and (max-width: 767px) {
		section {
			flex-direction: column;
			justify-content: center;
		}

		* {
			box-sizing: border-box;
		}

		.screen {
			width: 100%;
			padding-top: 2%;
		}
	}
</style>
