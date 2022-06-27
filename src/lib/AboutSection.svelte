<script lang="ts">
    import PrimaryHeader from './PrimaryHeader.svelte';
    import PrimarySub from './PrimarySub.svelte';
    import Button from './Button.svelte';
    import ScrollIcon from './ScrollIcon.svelte';
    import AureliusQuote from './AureliusQuote.svelte';
    import SectionTitle from './SectionTitle.svelte';
    import Cards from './Cards.svelte';
    import Footer from './Footer.svelte';
</script>

<main class="about">
    <div class="wrapper">
        <PrimaryHeader />
        <PrimarySub />
        <Button text="My Portfolio" />
        <ScrollIcon />
        <AureliusQuote />
        <SectionTitle text="Skills" />
        <Cards />
        <SectionTitle text="Contact Me" />
        <Cards />
        <Button text="My Portfolio" />
        <div class="buffer"></div>
    </div>
    <Footer />
</main>

<style lang="scss">
    @import "../styles/vars.scss";

    .about {
        @include offCenter;
        width: 100%;
        display: flex;
        align-items: center;
        flex-direction: column;
    }

    .wrapper {
        //@include offCenter;
        width: 86rem;
        text-align: center;
        height: auto;

        //z-index: 0;

        @media only screen and (max-width: 62.5em) {
            width: 85%;
        }

        @media only screen and (max-width: 44.375em) {
            width: 75%;
        }
    }

    .buffer {
        margin-bottom: 15rem;
    }
</style>