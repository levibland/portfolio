<script lang="ts">
    import PrimaryHeader from './PrimaryHeader.svelte';
    import PrimarySub from './PrimarySub.svelte';
    import Button from './Button.svelte';
    import ScrollIcon from './ScrollIcon.svelte';
    import AureliusQuote from './AureliusQuote.svelte';
    import SectionTitle from './SectionTitle.svelte';
    import Cards from './Cards.svelte';
    import Footer from './Footer.svelte';
    import Cybertruck from './Cybertruck.svelte';
    import Cube from './Cube.svelte';

    // Imgs
    import Tslogo from '../assets/tslogo.png';
    import Rustlogo from '../assets/rustlogo.png';
    import Reactlogo from '../assets/reactlogo.png';
    import Githublogo from '../assets/githublogo.png';
    import Linkedinlogo from '../assets/linkedinlogo.png';
    import Resumelogo from '../assets/resumelogo.png';

    let quote1 = "\"A man's worth is no greater than his ambitions.\" - ";
    let quote2 = "\"If a man knows not which port he sails, no wind is favorable.\" - ";
</script>

<main class="about">
    <div class="wrapper">
        <PrimaryHeader />
        <PrimarySub />
        <Button text="My Portfolio" fade={400} />
        <ScrollIcon />
        <AureliusQuote quote={quote1} name="Marcus Aurelius" />
        <Cybertruck />
        <SectionTitle text="Skills" show={930} />
        <Cards fade={1010} props={{ cardTexts: ["TypeScript", "Rust", "React"], cardImgs: [Tslogo, Rustlogo, Reactlogo], cardGradients: ["linear-gradient(15deg, #c9d6ff, #e2e2e2)", "linear-gradient(15deg, #c9d6ff, #e2e2e2)", "linear-gradient(15deg, #c9d6ff, #e2e2e2)"], cardShadowColors: ["rgb(201 214 255 / 30%) 0px 20px 40px, rgb(0 0 0 / 5%) 0px 1px 3px", "rgb(201 214 255 / 30%) 0px 20px 40px, rgb(0 0 0 / 5%) 0px 1px 3px", "rgb(201 214 255 / 30%) 0px 20px 40px, rgb(0 0 0 / 5%) 0px 1px 3px"], info: false }} />
        <AureliusQuote quote={quote2} name="Seneca" />
        <SectionTitle text="Info" show={2030} />
        <Cards fade={2110} props={{ cardTexts: ["Github", "Linkedin", "Resume"], cardImgs: [Githublogo, Linkedinlogo, Resumelogo], cardGradients: ["linear-gradient(15deg, #c9d6ff, #e2e2e2)", "linear-gradient(15deg, #c9d6ff, #e2e2e2)", "linear-gradient(15deg, #c9d6ff, #e2e2e2)"], cardShadowColors: ["rgb(201 214 255 / 30%) 0px 20px 40px, rgb(0 0 0 / 5%) 0px 1px 3px", "rgb(201 214 255 / 30%) 0px 20px 40px, rgb(0 0 0 / 5%) 0px 1px 3px", "rgb(201 214 255 / 30%) 0px 20px 40px, rgb(0 0 0 / 5%) 0px 1px 3px"], info: true, links: ["https://github.com/levibland", "https://www.linkedin.com/in/levi-bland-3586b3242/", "/"]}} />
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