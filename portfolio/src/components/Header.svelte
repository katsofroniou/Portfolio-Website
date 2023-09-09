<script lang="ts">
    // Components
    import NavBar from "./NavBar.svelte";
</script>

<main class="header">
    <div class="name">
        <h3>Kat Sofroniou</h3>
    </div>
    <div class="right">
        <div class="social">
            <a href="mailto:katerina@strawberrykat.co.uk">
                <img class='icon' src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAAACXBIWXMAAAsTAAALEwEAmpwYAAADf0lEQVR4nO2ay0tUURzHP6OlWPbEIiqJIGlRCT0werhIClokhJS0qJbiqv6FaKG2tF0LN0EtghYWRURBDyNLKHtsih4UWhllVhhm5sSJ34HDnTszZ2buHe9czgcuOPc87vl959zf73d+DjgcDofD4XA4HBXAKeADkIzpNQx0wX9bU+iKwAKLdXX6CTAsjdtj/DLsNHZCClqdeuJLvWFnCrphAjgOJIgXR4FxGwGScl0Caih9asQWr30p6Ib9wBf5+xOwl9JlFzAktowBh2wEUKwEbsnnaaA7XeiIKLOAE8CU2HAfWC1tVgIoysQXTMr9AWAN0WcV0Cdr/iNClBvt1gJoGoBX0vYDOEJ0OQh8k7W+Axp9+uQsgGI+cM7ocwFYSHSYB5wx1ncRWJymb14CmKHkp/R7G5GkaQvwUtb0S17bTBQkgGIt8Mjzjil/UWwSYuxvWctzYL3FuIIFUMwWw//KmJvAcorHUuCqJ0pVWo4NRADNbuP0+BnYR/jsKfCZgQqgv40rxrehnFEVwVMpJ1a9627kuesCFyDd+7iB4AjS74QigGYz8CIHj2yDN/JsK3C+UAVAtn+3ZUzOhMo9zhvznAWqKZzQBdAcAEazZGXp2Aq8lrHfgcMER9EE8OblUz55uRfv+eNhCOePUAXYIc5q0HBSKmfoMLz3baDWZ2yttCWlb4eMReZ6InOrZ0ROgBqgR8KgmuOpj5duMuqOX4EWo61F7ul6neprouZ6ZoTangKKNYEKUAa0GYtX5bSTGfIAtehe41mP5dKfezMYViVzTxgituURDgMTYCPQb4y7DtRZ5gztksXpsSNyz6YOWSfP0mP7ZS1FE2ABcNqotqiSUyu5M0e8fYP8nSutRrlrStak1haqAM3AeyMj65Z4PVPMlciiM9CPkjglghagDrhm9BmQc3iU6v063CalnrkuCAGqRGHteEYlTs/E+T8bCfn2R2Stk7JDq/MVoBl4Y4QelYouIfosEsNNH6WEsRZghdT89OfBAA4gM8Em4IFhx2UpjWcVYNz4R8KxLKlr1CkXG8Y8tmUUIClq+aWrpcoyeYWnbQRoIr405eIE7wF3PX3icM9agKRPxzjccwJguQP6gDuePnG4F2pBpBRIa+ewNKgfEsWVRiM7TKHTkwvE+VLlthQqRAS9E+J4DYnxpfRrF4fD4XA4HA6Hw0Hw/AMANKebGbHsPwAAAABJRU5ErkJggg==" alt="Email me!">
            </a>
            <a href="https://github.com/katsofroniou">
                <img class='icon' src="data:image/png;base64,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" alt="Github">
            </a>
            <a href="https://www.linkedin.com/in/katerina-s-319aba244">
                <img class="icon" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAAACXBIWXMAAAsTAAALEwEAmpwYAAADJ0lEQVR4nO2au2sVQRTGfyqKNyaFaFIE7ETQSmxUbDQgIiposBA7ESzs0oji8yZgqSgmpY9/wEIFoxZKNCiixiZNEkRRFBFFrw8MGFdGvoVl2cfduzdkdu98MGxy5szyzTdnzszOHXBwcHBwcEhDFzAAjAE/AM/SYri9ENdOmoS9QM2CzmUt34DeZnT+r154A9gMLMFeGG5bgJviPJNHhK7AyB+jeDgu7l8bnQ4DgZEvKvxIqDbS+KUam7AvKnrUB5MYM6Omxu0B2yjwKORns61DfTB9yQxPpYy2uuBZRNgaAR4CIwWzNVWAIsIJwCxHQBvQD0wB03qadbdCCwjQBjyW31vgtp6elqRK2QXol88lYKFs5jko+2lKLsCURtzvvA/z/ztgkpILMA0Mx9QZ+29aNAIWKQImKLkAVfkMhnLAkOynKLkAFWV7TyM+rKenj5LFtMA+oKJsP6mcMKmRt6HzhdwJLgA2An3AWeAMcBjYASy1TYDRlIPJ4Lf5swS/aZ3lHQJep/hdy3jENasCeHWUen0/B/5+BVzRVDoJXACeBg5oPwAbbBIgCnEChHE+JMI+TYMorAIeyPc90B3jl8TDWgG+qINpMHuM+2pzuQwCbNeGalcGbiuBP9ppduXgaIUAQaxV1r+qyDA/asyP8b2l9+3PwdEaAeaFckGw3I3ZU/SpfqgJ/ZhzAQ6o7idwETgIHFG2N/ajEW22qe5ODo7WCDCuOrMCBLFV9qiPqjWqG8/B0QoBugOrwPyIjP9L9eFd4ArZ3+TgaIUAm1J+vppQ/eqQvVP2jzk4WiGAP5fvxbxnTPXrQvZlsn/KwdEKAXbKbn7JjcIT1a8P2Z0AuAjATQFcDsAlQRpP1IlwqwBuGcTtA2h8mrTURshLKPX6pgkQV2ZNgFrENTki7uQkkRup03cm4TbqucBpcFS5nsCvI3BvODPG1Nic1xf9ouTzRhr3p4RmEeCfG5pzxszoVOh4unhcNJwIXJZe3uhLejU//UjoSckJc412cfRH3nDfnfelvVLRK1gxnPc0R1f+h1BVyeS7BZ2LKzVxrOYJewcHBwcHWgT/AD5aOQuaZNO6AAAAAElFTkSuQmCC" alt="LinkedIn">
            </a>
        </div>

        <div class="dl-toggle">
            <label>
                <input type="checkbox">
                <span class="slider"></span>
            </label>
        </div>
    </div>
</main>

<style lang="scss">
    @import '../styles/header.scss';
    @import '../styles/icons.scss';
</style>

