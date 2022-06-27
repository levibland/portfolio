<script lang="ts">
    export let text: String;
</script>

<div class="wrapper">
    <h1 class="section-title">
        {text}
        <span class="underline"></span>
    </h1>
    
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .wrapper {
        margin: auto;
        width: auto;
        height: auto;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        letter-spacing: 0.225rem;

        & .underline {
            display: block;
            height: .5rem;
            width: 100%;
            background: $hot-pink;
            margin-bottom: 5rem;
        }
    }

    .section-title {
        font-family: $primary-font;
        font-size: 5rem;
        color: $gray;
    }
</style>