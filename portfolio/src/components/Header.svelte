<script lang="ts">
    // Components
    import NavBar from "./NavBar.svelte";
</script>

<main class="header">
    <div class="top">
        <div class="name">
            <h3>Kat Sofroniou</h3>
        </div>
        <div class="dl-toggle">
            <button class="theme-button">dl</button>
        </div>
    </div>
    <div class="bottom">
        <div class="email">
            <a href="mailto:katerina@strawberrykat.co.uk"><button>email</button></a>
        </div>
        <div class="social">
            <p>Github</p>
            <p>LinkedIn</p>
        </div>
    </div>

    <NavBar/>
</main>

<style lang="scss">
    @import '../styles/header.scss';
</style>

