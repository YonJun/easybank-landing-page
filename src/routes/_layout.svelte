<script lang="ts">
    import Nav from "../components/Nav.svelte";
</script>

<style>
    :global(:root) {
        --nav-height: 60px;
        --dark-blue: hsl(233, 26%, 24%);
        --lime-green: hsl(136, 65%, 51%);
        --bright-cyan: hsl(192, 70%, 51%);
        --grayish-blue: hsl(233, 8%, 62%);
        --light-grayish-blue: hsl(220, 16%, 96%);
        --very-light-gray: hsl(0, 0%, 98%);
        --white: hsl(0, 0%, 100%);
    }
    main {
        /* background-color: red; */
        color: var(--dark-blue);
        overflow: hidden;
        position: relative;

        margin-top: var(--nav-height);
        background-color: var(--light-grayish-blue);
    }
</style>

<Nav />

<main>
    <slot />
</main>
