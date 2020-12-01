<script lang="ts">
    import Container from "../../components/Container.svelte";
    import EasybankCard from "../../components/EasybankCard.svelte";
    import type { EasybankItem } from "../../types/index.type.";
    const data: EasybankItem[] = [
        {
            icon: `assets/icon-online.svg`,
            title: `Online Banking`,
            description: `Our modern web and mobile applications allow you to keep track of your finances 
wherever you are in the world.`,
        },

        {
            icon: `assets/icon-budgeting.svg`,
            title: `Simple Budgeting`,
            description: `See exactly where your money goes each month. Receive notifications when you’re 
close to hitting your limits.`,
        },

        {
            icon: `assets/icon-onboarding.svg`,
            title: `Fast Onboarding`,
            description: `We don’t do branches. Open your account in minutes online and start taking control 
of your finances right away.`,
        },

        {
            icon: `assets/icon-api.svg`,
            title: `Open API`,
            description: `Manage your savings, investments, pension, and much more from one account. Tracking 
your money has never been easier.`,
        },
    ];
</script>

<style>
    .main {
        height: auto;
        padding-top: 5em;
        padding-bottom: 5em;
        width: 100%;
    }
    h2 {
        font-size: 30px;
    }
    p {
        color: var(--grayish-blue);
    }
    .row-1 {
        /* border: 1px solid blue; */
        width: 50%;
    }
    .row-2 {
        width: 100%;
        padding-top: 50px;
        /* border: 1px solid blue; */
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        grid-gap: 20px;
        display: grid;
        align-items: center; /* left and right */
        justify-content: center; /* up and down */
    }
    .item {
        /* border: 1px solid blue; */
    }
    @media (max-width: 960px) {
        .row-1 {
            width: 100%;
            text-align: center;
        }
    }
</style>

<Container>
    <div class="main">
        <div class="row-1">
            <h2>Why choose Easybank?</h2>
            <p>
                We leverage Open Banking to turn your bank account into your
                financial hub. Control your finances like never before.
            </p>
        </div>
        <div class="row-2">
            {#each data as item, i}
                <div class="item">
                    <EasybankCard props={item} />
                </div>
            {/each}
        </div>
    </div>
</Container>
