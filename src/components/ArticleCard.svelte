<script lang="ts">
    import type { ArticleItem } from "../types/index.type.";
    export let props: ArticleItem;
</script>

<style>
    .container {
        /* background-color: red; */
        /* border: 1px solid blue; */
        border-radius: 10px;
        width: 100%;
    }
    img {
        display: block;
        border-radius: 10px 10px 0 0;
        width: 100%;
        height: auto;
        min-height: 300px;
    }
    .autor {
        font-size: 12px;
    }

    .title {
        font-size: 20px;
    }

    .description {
        color: var(--grayish-blue);
    }
    .body {
        background-color: var(--white);
        border-radius: 0 0 10px 10px;

        padding: 20px;
    }
</style>

<div class="container">
    <img src={props.image} alt={props.title} />
    <div class="body">
        <div class="autor description">
            <p>{props.autor}</p>
        </div>
        <div class="title">
            <h3>{props.title}</h3>
        </div>
        <div class="description">
            <p>{props.description}</p>
        </div>
    </div>
</div>
