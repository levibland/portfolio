<script lang="ts">
    // Text
    export let text: String;

    let active: boolean = false;

    const activate = () => {
        active = true;
    }

    const deactivate = () => {
        setTimeout(() => {
            active = false;
        }, 2000);
    }
</script>

<div class="sub-word {active ? "active" : ""}" on:mouseenter={activate} on:mouseleave={deactivate}>
    <div class="sub-word-top">{text}</div>
    <div class="sub-word-bottom">{text}</div>
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .sub-word {
        display: inline-block;
        vertical-align: top;
        margin: 0 .5rem;
        height: 4rem;
        overflow: hidden;
        cursor: default;

        @media only screen and (max-width: 44.375em) {
            height: 2.5rem;
            margin: 0 0.3rem;
        }

        * {
            transition: all 250ms;
        }

        &.active * {
            transform: translateY(-4rem);

            @media only screen and (max-width: 44.375em) {
                transform: translateY(-3rem);
            }
        }
    }

    .sub-word-bottom {
        visibility: hidden;
        color: #5b6570;

        .sub-word.active & {
            visibility: visible;
        }
    }

    .sub-word-top {
        margin-bottom: 1rem;
    }
</style>