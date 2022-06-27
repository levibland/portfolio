<script lang="ts">
    //import { fly } from 'svelte/transition';

    // Loading animations
    let loading: boolean = true;

    setTimeout(() => {
        loading = false;
    }, 300);
</script>

<h1 class="primary-header {loading ? "slide-down" : ""}">
    <span>Hi, I'm</span>
    <span class="pink-text">&nbsp;Levi Bland</span>
</h1>

<style lang="scss">
    @import "../styles/vars.scss";

    .primary-header {
        margin: 0;
        font-size: 10.5rem;
        color: $white;
        letter-spacing: 4px;
        opacity: 1;
        visibility: visible;
        transform-origin: 50% 100%;
        transition: all 300ms ease-out;

        @media only screen and (max-width: 62.5em) {
            font-size: 8rem;
        }

        @media only screen and (max-width: 44.375em) {
            font-size: 5rem;
            margin-bottom: 1rem;
        }

        @media only screen and (max-width: 31.25em) {
            span {
                display: block;
            }
        }

        &.slide-down {
            opacity: 0;
            visibility: hidden;
            transform: translateY(-50%);
        }
    }

    .pink-text {
        color: $hot-pink;
    }
</style>