<script lang="ts">
    import PrimaryHeader from './PrimaryHeader.svelte';
    import PrimarySub from './PrimarySub.svelte';
    import Button from './Button.svelte';
</script>

<main class="about">
    <PrimaryHeader />
    <PrimarySub />
    <Button text="My Portfolio" />
</main>

<style lang="scss">
    @import "../styles/vars.scss";

    .about {
        @include offCenter;
        width: 86rem;
        text-align: center;

        //z-index: 0;

        @media only screen and (max-width: 62.5em) {
            width: 85%;
        }

        @media only screen and (max-width: 44.375em) {
            width: 75%;
        }
    }
</style>