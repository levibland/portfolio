<script lang="ts">
    export let text: String;
    export let show: number;

    // Scroll animation
    let y: number;
</script>

<svelte:window bind:scrollY={y} />

<div class="wrapper">
    <h1 class="section-title {y <= show ? "slide-down" : y >= show + 375 ? "slide-down" : ""}">
        {text}
        <span class="underline {y <= show ? "slide-up" : y >= show + 375 ? "slide-up" : ""}"></span>
    </h1>
    
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .wrapper {
        margin: auto;
        width: auto;
        height: auto;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        letter-spacing: 0.225rem;

        & .underline {
            display: block;
            height: .5rem;
            width: 100%;
            background: $hot-pink;
            margin-bottom: 5rem;
            transition: all 300ms ease-in-out;
            visibility: visible;
            opacity: 1;

            &.slide-up {
                transform: translateY(10rem);
                visibility: hidden;
                opacity: 0;
            }
        }
    }

    .section-title {
        font-family: $primary-font;
        font-size: 5rem;
        color: $gray;
        transition: all 300ms ease-in-out;
        visibility: visible;
        opacity: 1;

        &.slide-down {
            transform: translateY(-5rem);
            opacity: 0;
            visibility: hidden;
        }
    }
</style>