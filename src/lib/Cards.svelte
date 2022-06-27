<script lang="ts">
    import Card from './Card.svelte';
</script>

<div class="cards">
    <Card text="test" />
    <Card text="test" />
    <Card text="test" />
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