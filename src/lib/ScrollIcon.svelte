<script lang="ts">
    let loading: boolean = true;

    setTimeout(() => {
        loading = false;
    }, 500);

    // Scroll animation
    let y: number;
</script>

<svelte:window bind:scrollY={y} />

<div class="scroll-icon {loading ? "pop-in" : ""} {y >= 475 ? "pop-out" : ""}">
    <span class="wheel"></span>
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .scroll-icon {
        width: 4rem;
        height: 6rem;
        margin: auto;
        border: .3rem solid $gray;
        border-radius: 5rem;
        margin-top: 7rem;
        position: relative;
        cursor: default;
        transition: all 350ms $primary-cubic-bezier;
        opacity: 1;
        visibility: visible;

        &.pop-in {
            transform: scale(0);
            visibility: hidden;
            opacity: 0;
        }

        &.pop-out {
            transform: scale(1.25);
            visibility: hidden;
            opacity: 0;
        }

        & .wheel {
            position: absolute;
            width: 1em;
            height: 2rem;
            border: .175rem solid $gray;
            top: 15%;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 1rem;
            overflow: hidden;
        }

        & .wheel::before {
            content: '';
            background-image: linear-gradient(0deg, $gray 2px, transparent 1px);
            position: absolute;
            left: 0;
            right: 0;
            top: -100%;
            bottom: 0;
            background-size: 100% 6px;
            opacity: .5;
            animation: wheel-scroll .5s ease-in-out infinite;
        }

        @keyframes wheel-scroll {
            0% {
                transform: translateY(0);
                opacity: .5;
            }
            40%, 50% {
                opacity: .8;
            }
            90%, 100% {
                transform: translateY(50%);
                opacity: .5;
            }
        }
    }
</style>