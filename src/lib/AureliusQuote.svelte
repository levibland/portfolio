<script lang="ts">
    import { fly } from 'svelte/transition';
    let y: number;
</script>

<svelte:window bind:scrollY={y} />


<div class="wrapper">
    {#if y >= 500}
    <h1 class="quote" in:fly={{ x: -200, duration: 500 }} out:fly={{ x: 200, duration: 500 }}>"A man's worth is no greater than his ambitions." - <span class="pink-text">&nbsp;Marcus Aurelius</span></h1>
    {/if}
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .wrapper {
        margin-top: 25rem !important;
        //margin-bottom: 25rem !important;
        margin: auto;
        width: 70rem;
        height: 40rem;
    }

    .quote {
        font-size: 4rem;
        font-family: $display-font;
        color: $gray;

        & .pink-text {
            color: $hot-pink;
            font-family: $primary-font;
        }
    }
</style>