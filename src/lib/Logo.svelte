<script lang="ts">
    import { Link } from 'svelte-routing';

    let loading: boolean = true;

    setTimeout(() => {
        loading = false;
    }, 200);
</script>

<div class="wrapper {loading ? "slide-right" : ""}">
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
        transition: all 300ms $primary-cubic-bezier;
        position: absolute;
        visibility: visible;
        opacity: 1;

        &:hover {
            transform: scale(1.1);
        }

        &.slide-right {
            transform: translateX(-10rem);
            visibility: hidden;
            opacity: 0;
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