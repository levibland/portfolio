<script lang="ts">
    import { Link } from "svelte-routing";

    export let text: String;
    export let fade: number;

    let loading: boolean = true;

    setTimeout(() => {
        loading = false;
    }, 350);

    // Scroll animation
    let y: number;
</script>

<svelte:window bind:scrollY={y} />

<Link to="/">
    <div class="button-link {loading ? "slide-up" : ""} {y >= fade ? "rotate-right" : ""}">
        <button class="button-top">{text}</button>
        <button class="button-bottom">{text}</button>
    </div>
</Link>

<style lang="scss">
    @import '../styles/vars.scss';

    .button-link {
        display: block;
        margin: auto;
        margin-top: 5rem;
        height: 5rem;
        width: 16rem;
        overflow: hidden;
        text-decoration: none;
        opacity: 1;
        visibility: visible;
        transform-origin: 50% 100%;
        transition: all 300ms ease-in-out;

        * {
            transition: all 150ms;
            display: block;
            width: 100%;
            height: 4.5rem;
            line-height: 1;
            font-size: 2rem;
            text-align: center;
            border: 2px solid $hot-pink;
            border-radius: 7px;
            background-color: $base-dark;
            color: $hot-pink;
            font-family: $primary-font;
        }

        &:hover * {
            transform: translateY(-5.5rem);
            cursor: pointer;
        }

        &.slide-up {
            visibility: hidden;
            opacity: 0;
            transform: translateY(4rem);
        }

        &.rotate-right {
            visibility: hidden;
            opacity: 0;
            transform: translateX(-5rem);
        }
    }

    .button-bottom {
        transition: all 150ms;
        display: block;
        width: 100%;
        height: 4.5rem;
        line-height: 1;
        font-size: 2rem;
        border: 2px solid $hot-pink;
        border-radius: 7px;
        background-color: $hot-pink;
        color: $white;
        font-family: $primary-font;
        margin-top: 1rem;
    }
</style>