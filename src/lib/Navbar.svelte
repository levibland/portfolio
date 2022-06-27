<script lang="ts">
    import Logo from "./Logo.svelte";
    import Navigation from './Navigation.svelte';
</script>

<div class="navbar">
    <Logo />
    <Navigation />
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .navbar {
        width: 100%;
        height: 9.25rem;
        background: $base-dark;
        position: fixed;
        z-index: 1000;
    }
</style>