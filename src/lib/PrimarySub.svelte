<script lang="ts">
    import Word from './Word.svelte';

    // Loading animations
    let loading: boolean = true;

    setTimeout(() => {
        loading = false;
    }, 300);

    // Scroll animation
    let y: number;
</script>

<svelte:window bind:scrollY={y} />

<sub class="primary-sub">
    <div class="line-wrapper {loading ? "slide-left" : ""} {y >= 250 ? "slide-right" : ""}">
        <Word text="I'm" />
        <Word text="a" />
        <Word text="software" />
        <Word text="engineer" />
        <Word text="based" />
        <Word text="in" />
        <Word text="Auckland," />
        <Word text="New" />
        <Word text="Zealand" />
    </div>
    <div class="line-wrapper {loading ? "slide-right" : ""} {y >= 270 ? "slide-left" : ""}">
        <Word text="Get" />
        <Word text="in" />
        <Word text="touch" />
        <Word text="and" />
        <Word text="let's" />
        <Word text="make" />
        <Word text="something" />
        <Word text="special" />
    </div>
</sub>

<style lang="scss">
    @import "../styles/vars.scss";

    .primary-sub {
        color: $gray;
        line-height: 1;
        font-size: 3rem;
        display: block;

        @media only screen and (max-width: 44.375em) {
            font-size: 2rem;
        }

        @media only screen and (max-width: 31.275em) {
            font-size: 1.75rem;
        }
    }

    .line-wrapper {
        opacity: 1;
        visibility: visible;
        transform-origin: 50% 100%;
        transition: all 300ms ease-out;

        &.slide-left {
            opacity: 0;
            visibility: hidden;
            transform: translateX(15%);
        }

        &.slide-right {
            opacity: 0;
            visibility: hidden;
            transform: translateX(-15%);
        }
    }
</style>