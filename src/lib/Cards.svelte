<script lang="ts">
    import Card from './Card.svelte';

    export let fade: number;
</script>

<div class="cards">
    <Card text="test" fade={fade} />
    <Card text="test" fade={fade} />
    <Card text="test" fade={fade} />
</div>

<style lang="scss">
    .cards {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        margin-bottom: 25rem;
    }
</style>