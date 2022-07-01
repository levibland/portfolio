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
        background: rgba(34, 38, 42, 0.7);
        position: fixed;
        z-index: 1000;
        //backdrop-filter: blur(20px);
    }
</style>