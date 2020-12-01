<script lang="ts">
    import Container from "../../components/Container.svelte";
    import ArticleCard from "../../components/ArticleCard.svelte";
    import type { ArticleItem } from "../../types/index.type.";
    const data: ArticleItem[] = [
        {
            image: `assets/image-currency.jpg`,
            autor: `By Claire Robinson`,
            title: `Receive money in any currency with no fees`,
            description: `The world is getting smaller and we’re becoming more mobile. So why should you be 
forced to only receive money in a single …`,
        },
        {
            image: `assets/image-restaurant.jpg`,
            autor: `By Wilson Hutton`,
            title: `Treat yourself without worrying about money`,
            description: `Our simple budgeting feature allows you to separate out your spending and set 
realistic limits each month. That means you …`,
        },
        {
            image: `assets/image-plane.jpg`,
            autor: `By Wilson Hutton`,
            title: `Take your Easybank card wherever you go`,
            description: `We want you to enjoy your travels. This is why we don’t charge any fees on purchases 
while you’re abroad. We’ll even show you …`,
        },
        {
            image: `assets/image-restaurant.jpg`,
            autor: `By Claire Robinson`,
            title: `Our invite-only Beta accounts are now live!`,
            description: `After a lot of hard work by the whole team, we’re excited to launch our closed beta. 
It’s easy to request an invite through the site …`,
        },
    ];
</script>

<style>
    .container {
        background-color: var(--very-light-gray);
    }
    .main {
        height: auto;
        padding-top: 5em;
        padding-bottom: 5em;
        width: 100%;
    }
    h2 {
        font-size: 30px;
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

<div class="container">
    <Container>
        <div class="main">
            <div class="row-1">
                <h2>Latest Articles</h2>
            </div>
            <div class="row-2">
                {#each data as item, i}
                    <div class="item">
                        <ArticleCard props={item} />
                    </div>
                {/each}
            </div>
        </div>
    </Container>
</div>
