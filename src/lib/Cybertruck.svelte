<script lang="ts">
    import Truck from '../assets/cybertruck.svg';
    let y: number;
    let last_y: [number, number] = [0, 0];

    // Transform shite
    let initial = -100;

    function direction(ys: [number, number]): boolean {
        if (ys[0] > ys[1]) {
            return false;
        } else {
            return true;
        }
    }

    $: {
        last_y[0] = last_y[1];
        last_y[1] = y;
    };

    //$: console.log(y);

    $: if (y >= 400 && direction(last_y) == true) {
        if (initial < 100) {
            initial += 1;
        }
    } else if (y < 1100 && direction(last_y) == false) {
        if (initial > -100) {
            initial -= 1;
        }
    };
</script>

<svelte:window bind:scrollY={y} />

<div class="truck-container" style="--translate:translateX({initial}vw);">
    <span class="image-wrapper">
        <img class="truck" src={Truck} alt="Cybertruck" />
    </span>
</div>

<style lang="scss">
    .truck-container {
        margin-left: auto;
        margin-right: auto;
        overflow: hidden;
        max-width: 16%;
        position: relative;
        display: block;
        margin-bottom: 10rem;
        transition: transform 200ms linear;
        transform: var(--translate);

        & .image-wrapper {
            display: block;
            position: relative;
            max-width: 100%;

            & .truck {
                max-width: 100%;
                height: auto;
            }
        }
    }
</style>