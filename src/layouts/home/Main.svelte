<script lang="ts">
    import Button from "../../components/Button.svelte";

    import Container from "../../components/Container.svelte";
</script>

<style>
    .main,
    .text {
        height: auto;
        min-height: 75vh;
        width: 100%;
    }
    .main {
        background-color: var(--very-light-gray);
        position: relative;
        overflow: hidden;
    }
    .backdrop {
        top: -30vh;
        right: -20vw;
        position: absolute;
        width: 75%;
        height: 80vh;
    }

    .text {
        display: flex;
        align-items: center;
        justify-content: center;
        /* background-color: red; */
    }
    .body {
        width: 40%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    .body h1 {
        font-size: 40px;
    }
    .body h4 {
        color: var(--grayish-blue);
    }
    .row {
        padding-top: 20px;
    }
    .desktop {
        display: block;
    }
    .mobile {
        display: none;
    }

    .bg-mockups {
        top: -10vh;
        right: -10vw;
        position: absolute;
        /* border: 1px solid blue; */
        display: block;
    }
    .bg-mockups img {
        width: 40vw;
    }

    @media (max-width: 960px) {
        .desktop {
            display: none;
        }
        .mobile {
            display: block;
        }

        .bg-mockups {
            top: -50px;
            left: 0;
            right: 0;
            width: 100%;
        }
        .backdrop {
            top: 0;
            left: 0;
            width: 100%;
            position: relative;
            height: 60vh;
        }
        .main,
        .text {
            min-height: 40vh;
        }
        .text {
            position: relative;
            z-index: 9;
            text-align: center;
        }
        .body {
            width: 100%;
        }

        .bg-mockups {
            width: 100%;
        }
        .bg-mockups img {
            width: 100%;
        }
    }
</style>

<div class="main">
    <div class="backdrop">
        <img
            class="desktop"
            src="/assets/bg-intro-desktop.svg"
            width="100%"
            height="auto"
            alt="bg-intro-desktop" />
        <img
            class="mobile"
            src="/assets/bg-intro-mobile.svg"
            width="100%"
            height="auto"
            alt="bg-intro-mobile" />
    </div>
    <div class="text">
        <Container>
            <div class="body">
                <h1>Next generation digital banking</h1>
                <h4>
                    Take your financial life online. Your Easybank account will
                    be a one-stop-shop for spending, saving, budgeting,
                    investing, and much more.
                </h4>
                <div class="row">
                    <Button label="Request Invite" />
                </div>
            </div>
        </Container>
    </div>
</div>
<div class="bg-mockups">
    <img src="/assets/image-mockups.png" height="auto" alt="bg-intro-desktop" />
</div>
