<script lang="ts">
    export let quote: string;
    export let name: string;

    let y: number;
</script>

<svelte:window bind:scrollY={y} />


<!--<div class="wrapper">
    {#if y >= 500}
    <h1 class="quote" in:fly={{ x: -200, duration: 500 }} out:fly={{ x: 200, duration: 500 }}>"A man's worth is no greater than his ambitions." - <span class="pink-text">&nbsp;Marcus Aurelius</span></h1>
    {/if}
</div>-->
<!--<h1 class="quote">
    <div class="wrapper">
    <span class="quote-body {y <= 500 ? "slide-right" : ""}">"A man's worth is no greater than his ambitions." -</span>
    </div>
    <div class="wrapper {y <= 500 ? "slide-left" : ""}">
    <span class="pink-text">&nbsp;Marcus Aurelius</span>
    </div>
</h1>-->

<div class="wrapper {y <= 400 ? "slide-in" : y >= 900 ? "slide-in2" : ""}">
    <span class="quote">
        {quote} 
    </span>
    <span class="pink-text {y >= 500 ? "fade-in" : ""}">
        &nbsp;{name}
    </span>
</div>


<style lang="scss">
    @import '../styles/vars.scss';

    .wrapper {
        margin-top: 25rem !important;
        width: 100%;
        margin-bottom: 25rem !important;
        //margin: auto;
        font-size: 4rem;
        color: $gray;
        font-family: $display-font;
        display: block;
        transition: all 400ms ease-in-out;
        opacity: 1;
        visibility: visible;

        @media only screen and (max-width: 35em) {
            font-size: 3rem;
        }

        /*&.slide-in {
            transform: translateX(-20rem);
            visibility: hidden;
            opacity: 0;
        }

        &.slide-in2 {
            transform: translateX(20rem);
            visibility: hidden;
            opacity: 0;
        }*/

        & .pink-text {
            font-family: $primary-font;
            color: $hot-pink;
        }
    }

    /*.wrapper {
        margin-top: 25rem !important;
        //margin-bottom: 25rem !important;
        margin: auto;
        width: 70rem;
        height: 40rem;
    }*/

    /*.quote {
        font-size: 4rem;
        font-family: $display-font;
        color: $gray;
        margin-top: 25rem !important;
        margin-bottom: 25rem !important;
        transition: all 500ms $primary-cubic-bezier;
        visibility: visible;
        opacity: 1;

        & .pink-text {
            color: $hot-pink;
            font-family: $primary-font;
            transition: all 600ms $primary-cubic-bezier;
            opacity: 1;
            visibility: visible;

            &.slide-left {
                transform: translateX(10rem);
                opacity: 0;
                visibility: hidden;
            }
        }

        & .quote-body {
            transition: all 500ms $primary-cubic-bezier;
            opacity: 1;
            visibility: visible;

            &.slide-right {
                transform: translateX(-10rem);
                opacity: 0;
                visibility: hidden;
            }
        }
    }*/
</style>