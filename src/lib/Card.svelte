<script lang="ts">
    export let text: String;
    export let fade: number;
    export let imgPath: string;
    export let gradient: string;
    export let shadowColor: string;
    export let cursor: string;
    export let link: string;

    // Scroll animation
    let y: number;
</script>

<svelte:window bind:scrollY={y} />


<a href={link} class="card {y <= fade ? "animate" : y >= fade + 450 ? "animate-opposite" : ""}" style="--gradient:{gradient};--shadowColor:{shadowColor};--cursor:{cursor};">
    <img class="card-img" src={imgPath} alt="Logo" />
    {text}
</a>

<style lang="scss">
    @import '../styles/vars.scss';

    a {
        display: block;
    }

    .card {
        width: 30rem;
        height: 35rem;
        background: var(--gradient);
        box-shadow: var(--shadowColor);
        border-radius: 40px;
        margin-left: 25px;
        margin-right: 25px;
        transition: all 300ms ease-in-out;
        visibility: visible;
        opacity: 1;
        display: flex;
        cursor: var(--cursor);
        flex-direction: column;
        align-items: center;
        justify-content: center;
        color: $mid-dark;
        font-size: 4rem;

        @media only screen and (max-width: 60em) {
            margin-bottom: 5rem;

            &:hover {
                transform: scale(1.05);
            }
        }

        & .card-img {
            width: auto;
            height: 10rem;
            margin-bottom: 3rem;
        }

        &:hover {
            transform: scale(1.05);
        }

        &:nth-child(1).animate {
            transform: translateX(-5rem);
            opacity: 0;
            visibility: hidden;
            
            @media only screen and (max-width: 60em) {
                opacity: 1;
                visibility: visible;
                transform: translate(0, 0);
            }
        }

        &:nth-child(3).animate {
            transform: translateX(5rem);
            opacity: 0;
            visibility: hidden;

            @media only screen and (max-width: 60em) {
                opacity: 1;
                visibility: visible;
                transform: translate(0, 0);
            }
        }

        &:nth-child(2).animate {
            transform: scale(0.75);
            opacity: 0;
            visibility: hidden;
            
            @media only screen and (max-width: 60em) {
                opacity: 1;
                visibility: visible;
                transform: translate(0, 0);
            }
        }

        &:nth-child(1).animate-opposite {
            transform: translateX(-5rem);
            opacity: 0;
            visibility: hidden;

            @media only screen and (max-width: 60em) {
                opacity: 1;
                visibility: visible;
                transform: translate(0, 0);
            }
        }

        &:nth-child(3).animate-opposite {
            transform: translateX(5rem);
            opacity: 0;
            visibility: hidden;
            
            @media only screen and (max-width: 60em) {
                opacity: 1;
                visibility: visible;
                transform: translate(0, 0);
            }
        }

        &:nth-child(2).animate-opposite {
            transform: scale(0.75);
            opacity: 0;
            visibility: hidden;
            
            @media only screen and (max-width: 60em) {
                opacity: 1;
                visibility: visible;
                transform: translate(0, 0);
            }
        }
    }
</style>