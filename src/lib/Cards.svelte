<script lang="ts">
    import Card from './Card.svelte';
    import Tslogo from '../assets/tslogo.png';

    interface CardProps {
        cardTexts: [String, String, String],
        cardImgs: [string, string, string],
        cardGradients: [string, string, string],
        cardShadowColors: [string, string, string],
        info: boolean,
        links?: [string, string, string],
    }

    export let fade: number;
    export let props: CardProps;

    let cursor = props.info ? "pointer" : "default";
    let links = props.links != null ? props.links : [" ", " ", " "]

</script>

<div class="cards">
    <Card text={props.cardTexts[0]} fade={fade} imgPath={props.cardImgs[0]} gradient={props.cardGradients[0]} shadowColor={props.cardShadowColors[0]} cursor={cursor} link={links[0]} />
    <Card text={props.cardTexts[1]} fade={fade} imgPath={props.cardImgs[1]} gradient={props.cardGradients[1]} shadowColor={props.cardShadowColors[1]} cursor={cursor} link={links[1]} />
    <Card text={props.cardTexts[2]} fade={fade} imgPath={props.cardImgs[2]} gradient={props.cardGradients[2]} shadowColor={props.cardShadowColors[2]} cursor={cursor} link={links[2]} />
</div>

<style lang="scss">
    .cards {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        margin-bottom: 25rem;

        @media only screen and (max-width: 60em) {
            flex-direction: column;
        }
    }
</style>