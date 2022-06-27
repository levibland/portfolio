<script lang="ts">
    export let text: String;
    export let fade: number;

    // Scroll animation
    let y: number;
</script>

<svelte:window bind:scrollY={y} />

<div class="card {y <= fade ? "animate" : y >= fade + 450 ? "animate-opposite" : ""}">

</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .card {
        width: 30rem;
        height: 35rem;
        background: $gray;
        border-radius: 40px;
        margin-left: 25px;
        margin-right: 25px;
        transition: all 300ms ease-in-out;
        visibility: visible;
        opacity: 1;

        &:hover {
            transform: scale(1.05);
        }

        &:nth-child(1).animate {
            transform: translateX(-5rem);
            opacity: 0;
            visibility: hidden;
        }

        &:nth-child(3).animate {
            transform: translateX(5rem);
            opacity: 0;
            visibility: hidden;
        }

        &:nth-child(2).animate {
            transform: translateY(8rem);
            opacity: 0;
            visibility: hidden;
        }

        &:nth-child(1).animate-opposite {
            transform: translateX(-5rem);
            opacity: 0;
            visibility: hidden;
        }

        &:nth-child(3).animate-opposite {
            transform: translateX(5rem);
            opacity: 0;
            visibility: hidden;
        }

        &:nth-child(2).animate-opposite {
            transform: translateY(-8rem);
            opacity: 0;
            visibility: hidden;
        }
    }
</style>