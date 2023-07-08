<script lang="ts"></script>

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
    <div class="projectsContainer">
        <div class="project">1</div>
        <div class="project">2</div>
        <div class="project">3</div>
        <div class="project">4</div>
        <div class="project">5</div>
        <div class="project">6</div>
    </div>
</main>

<style lang="scss">

    .projectsContainer {
        display: flex;
        flex-direction: row;
    }

</style>