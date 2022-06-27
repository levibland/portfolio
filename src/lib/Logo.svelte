<script lang="ts">
    import { Link } from 'svelte-routing';
</script>

<div class="wrapper">
    <Link to="/">
        <h1 class="logo">
            Levi <span class="pink-text">Bland</span>
        </h1>
    </Link>
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .wrapper {
        margin-top: 2.5rem;
        margin-left: 3.5rem;
        transition: all 300ms ease-in-out;
        position: absolute;

        &:hover {
            transform: scale(1.1);
        }
    }
    
    .logo {
        font-size: 3.5rem;
        color: $white;
        letter-spacing: 0.15rem;
    }

    .pink-text {
        color: $hot-pink;
    }
</style>