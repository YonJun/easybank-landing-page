<script lang="ts">
    import { afterUpdate } from "svelte";

    export let enabled: boolean;
    export let onClose: () => void;

    function handleClose(e: MouseEvent) {
        const target = e.target as HTMLDivElement;

        console.log("handleClose", target.id);
        if (target.id === "modal") {
            onClose();
        }
    }

    afterUpdate(() => {
        if (enabled) window.document.body.style.overflow = "hidden";
        else window.document.body.style.overflow = "auto";
    });

    // Get the modal
</script>

<style>
    #modal {
        display: flex;
        justify-content: center;
        position: fixed;
        z-index: 1;
        left: 0;
        top: var(--nav-height);
        width: 100%;
        height: 100%;
        overflow: auto;
        background-image: linear-gradient(
            hsl(233, 26%, 24%, 0.5),
            rgba(0, 0, 0, 0)
        );
        -webkit-animation-name: fadeIn;
        -webkit-animation-duration: 0.4s;
        animation-name: fadeIn;
        animation-duration: 0.4s;
    }

    .modal-content {
        position: fixed;
        top: 100px;
        width: 100%;
        -webkit-animation-name: slideIn;
        -webkit-animation-duration: 0.4s;
        animation-name: slideIn;
        animation-duration: 0.4s;
    }

    .modal-body {
        padding: 2px 16px;
    }

    @-webkit-keyframes slideIn {
        from {
            top: -300px;
            opacity: 0;
        }
        to {
            top: var(--nav-height);
            opacity: 1;
        }
    }

    @keyframes slideIn {
        from {
            top: -300px;
            opacity: 0;
        }
        to {
            top: var(--nav-height);
            opacity: 1;
        }
    }

    @-webkit-keyframes fadeIn {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
</style>

{#if enabled}
    <div id="modal" on:click={handleClose}>
        <div class="modal-content">
            <div class="modal-body">
                <slot />
            </div>
        </div>
    </div>
{/if}
