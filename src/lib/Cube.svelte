<script lang="ts">
    import Cube from '../assets/cube.svg';
</script>

<div class="cube-container">
    <span class="image-wrapper">
        <img class="cube" src={Cube} alt="Cube" />
    </span>
</div>

<style lang="scss">
    .cube-container {
        max-width: 66px;
        margin-top: 0;
        margin-bottom: 0;
        margin-left: auto;
        margin-right: 0;
        overflow: hidden;
        position: relative;
        display: block;

        & .image-wrapper {
            display: block;
            position: relative;
            max-width: 100%;

            & .cube {
                max-width: 100%;
                height: auto;
            }
        }
    }
</style>