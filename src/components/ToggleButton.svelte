<script lang="ts">
    import Container from "./Container.svelte";
    import Modal from "./Modal.svelte";
    let open = false;
    function close() {
        open = !open;
    }
    function linkClick(e: MouseEvent) {
        e.preventDefault();
        close();
    }
</script>

<style>
    .container {
        border-radius: 10px;
        background-color: var(--white);
        padding: 20px 0 10px 0;
    }
    ul {
        /* background-color: rebeccapurple; */
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 0;
        list-style-type: none;
    }
    p {
        text-transform: capitalize;
        text-decoration: none;
        /* background-color: red; */
        text-align: center;
        cursor: pointer;
    }
    li {
        padding: 0;
        padding: 1em 0.5em;
        display: block;
        text-align: center;
    }
    .btn-toggle {
        cursor: pointer;
    }
    .btn-toggle img {
        display: block;
        width: 100%;
        height: auto;
    }
</style>

<div on:click={close} class="btn-toggle">
    {#if open}
        <img alt="close" src="/assets/icon-close.svg" />
    {:else}<img alt="hamburger" src="/assets/icon-hamburger.svg" />{/if}
</div>
<Modal enabled={open} onClose={close}>
    <Container>
        <nav class="container">
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
        </nav>
    </Container>
</Modal>
