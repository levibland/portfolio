<script lang="ts">
    import { Link } from 'svelte-routing';

    // toggling functionality
    let open: boolean = false;

    const toggle = () => {
        open = !open;
    }

    const close = () => {
        open = false;
    }

    // page load animations
    let loading: boolean = true;

    setTimeout(() => {
        loading = false;
    }, 200);
</script>

<div>
    <input class="nav-checkbox" type="checkbox" id="nav-toggle" checked="{open}" on:click={toggle} />
    <label class="nav-button {loading ? "slide-left" : ""}" for="nav-toggle">
        <div class="nav-line"></div>
        <div class="nav-line"></div>
        <div class="nav-line"></div>
    </label>
    <nav class="nav">
        <ul class="nav-list">
            <li class="nav-item">
                <Link to="/" on:click={close}><div class="nav-link"><span class="white">About</span></div></Link>
            </li>
            <li class="nav-item">
                <Link to="/" on:click={close}><div class="nav-link"><span class="white">Portfolio</span></div></Link>
            </li>
        </ul>
    </nav>
</div>

<style lang="scss">
    @import '../styles/vars.scss';

    .nav-checkbox {
        display: none;
    }

    .nav-button {
        position: fixed;
        top: 3rem;
        right: 4rem;
        z-index: 1000;
        width: 4.2rem;
        cursor: pointer;
        opacity: 1;
        transition: all 300ms $primary-cubic-bezier;
        visibility: visible;

        @media only screen and (min-width: 120em) {
            width: 6.2rem;
        }

        &.slide-left {
            transform: translateX(5rem);
            visibility: hidden;
            opacity: 0;
        }

        .nav-checkbox:checked + & {
            transform: scale(1.4);
            transition: all 300ms $primary-cubic-bezier;
        }

        .nav-checkbox:checked + &:hover {
            transform: scale(1.6);
        }
    }

    .nav-line {
        display: inline-block;
        width: 100%;
        height: 2px;
        background-color: $gray;
        transition: all 300ms $primary-cubic-bezier, background-color .3s ease-in;
        vertical-align: middle;
        margin: auto;

        &:nth-child(1), &:nth-child(3) {
            transform-origin: 5.5% 50%;

            @media only screen and (min-width: 100em) {
                transform-origin: 20.5% 50%;
            }
        }

        .nav-button:hover &:nth-child(1) {
            transform: translateY(-0.4rem);
        }

        .nav-button:hover &:nth-child(3) {
            transform: translateY(0.4rem);
        }

        .nav-checkbox:checked + .nav-button &:nth-child(2) {
            transform: translateX(-100%);
            opacity: 0;
            visibility: hidden;
        }

        .nav-checkbox:checked + .nav-button &:nth-child(1) {
            transform: rotate(45deg);
        }

        .nav-checkbox:checked + .nav-button &:nth-child(3) {
            transform: rotate(-45deg);
        }

        .nav-checkbox:checked + .nav-button & {
            background: $white;
            transition: all 300ms $primary-cubic-bezier, background-color 300ms ease-out;
        }
    }

    .nav {
        position: fixed;
        z-index: -1;
        top: 0;
        left: 0;
        background: $mid-dark;
        width: 100%;
        height: 0;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: all 300ms ease-out;

        .nav-checkbox:checked ~ & {
            height: 100%;
            z-index: 900;
        }
    }

    .nav-list {
        list-style: none;
        width: 60rem;
        margin: auto;

        @media only screen and (max-width: 31.25em) {
            width: 80%;
        }

        @media only screen and (min-width: 100em) {
            width: 80rem;
        }
    }

    .nav-item {
        width: 100%;
    }

    .nav-link {
        width: 100%;
        padding: 2.5rem 0;
        display: block;
        text-align: center;
        font-size: 3.5rem;
        text-decoration: none;
        position: relative;
        background: $mid-dark-2;
        cursor: pointer;

        & .white {
            color: #fff;
            position: relative;
        }

        &::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: #252a2e;
            transform: scaleX(0);
            transition: all 300ms ease-out;
        }

        &:hover, &:active, &:focus {
            text-decoration: none;

            &::before {
                transition: all 300ms $primary-cubic-bezier;
                transform: scaleX(1);
            }
        }
    }
</style>