<script lang="ts">
    export let label: string;
</script>

<style>
    .btn {
        background: none;
        color: inherit;
        border: none;
        padding: 0;
        cursor: pointer;
    }

    .btn {
        padding: 10px 25px 10px 25px;
        border-radius: 20px;
        color: white;
        text-transform: capitalize;
        background-image: linear-gradient(
            to right,
            var(--lime-green),
            var(--bright-cyan)
        );
    }
    .btn:hover {
        opacity: 0.8;
    }
</style>

<buton class="btn">{label}</buton>
