<script lang="ts">
    import type { EasybankItem } from "../types/index.type.";
    export let props: EasybankItem;
</script>

<style>
    .container {
        width: 100%;
    }

    .title {
        font-size: 20px;
    }

    .description {
        color: var(--grayish-blue);
    }
    .body {
        padding-top: 20px;
    }

    @media (max-width: 960px) {
        .container {
            text-align: center;
        }
    }
</style>

<div class="container">
    <img src={props.icon} alt={props.title} />
    <div class="body">
        <div class="title">
            <h3>{props.title}</h3>
        </div>
        <div class="description">
            <p>{props.description}</p>
        </div>
    </div>
</div>
