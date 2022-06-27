<script lang="ts">
    export let text: String;
</script>

<div class="card">

</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .card {
        width: 30rem;
        height: 35rem;
        background: $gray;
        border-radius: 40px;
        margin-left: 25px;
        margin-right: 25px;
        transition: all 200ms ease-in-out;

        &:hover {
            transform: scale(1.05);
        }
    }
</style>