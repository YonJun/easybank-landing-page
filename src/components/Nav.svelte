<script lang="ts">
    import Button from "./Button.svelte";

    import Container from "./Container.svelte";
    import ToggleButton from "./ToggleButton.svelte";

    const linkClick = (e: Event) => {
        // e.preventDefault();
    };
</script>

<style>
    .navigation {
        position: fixed;
        top: 0;
        left: 0;
        background-color: var(--white);
        width: 100%;
        z-index: 10;
    }
    nav {
        height: var(--nav-height);
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    .links {
        width: 35%;
        text-transform: capitalize;
        color: var(--grayish-blue);
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    ul {
        margin: 0;
        padding: 0;
    }

    /* clearfix */
    ul::after {
        content: "";
        display: block;
        clear: both;
    }

    li {
        display: block;
    }

    p:hover {
        position: relative;
        display: inline-block;
        cursor: pointer;
        color: var(--dark-blue);
    }

    p:hover::after {
        position: absolute;
        content: "";
        width: calc(100% - 1em);
        height: 4px;
        background-image: linear-gradient(
            to right,
            var(--lime-green),
            var(--bright-cyan)
        );
        display: block;
        bottom: -1px;
    }

    p {
        padding: 1em 0.5em;
        display: block;
    }

    .toggle-button-container {
        display: none;
    }

    @media (max-width: 960px) {
        .toggle-button-container {
            display: block;
        }
        .links,
        .button-container {
            display: none;
        }
    }
</style>

<div class="navigation">
    <Container>
        <nav>
            <ul>
                <li><img src="/assets/logo.svg" alt="Logo easybank" /></li>
            </ul>
            <ul class="links">
                <li>
                    <p on:click={linkClick}>home</p>
                </li>
                <li>
                    <p on:click={linkClick}>about</p>
                </li>
                <li>
                    <p on:click={linkClick}>contact</p>
                </li>
                <li>
                    <p on:click={linkClick}>blog</p>
                </li>
                <li>
                    <p on:click={linkClick}>careers</p>
                </li>
            </ul>
            <ul>
                <li class="button-container">
                    <Button label="request invite" />
                </li>
                <li class="toggle-button-container">
                    <ToggleButton />
                </li>
            </ul>
        </nav>
    </Container>
</div>
