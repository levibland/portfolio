<script lang="ts">
  import { Router, Route } from "svelte-routing";
  import Home from "./routes/Home.svelte";

  export let url = "";
</script>

<Router url="{url}">
  <div>
    <Route path="/"><Home /></Route>
  </div>
</Router>

<style lang="scss">
  @import './styles/vars.scss';

  :global(*, *::after, *::before) {
    margin: 0;
    padding: 0;
    box-sizing: inherit;
  }

  :global(body) {
    background: $base-dark;
    font-family: $primary-font;
    box-sizing: border-box;
    height: 100%;
    overflow-x: hidden;
  }

  // set up rem/em
  :global(html) {
    height: 100%;
    font-size: 62.5%;
    scroll-behavior: smooth;
    //transform: translateZ(0);

    @media only screen and (max-width: 62.5em) {
        font-size: 55.5%;
    }

    @media only screen and (max-width: 37.5em)
    {
        font-size: 50%;
    }

    @media only screen and (min-width: 143.75em)
    {
        font-size: 90%;
    }

    @media only screen and (min-width: 187.5em)
    {
        font-size: 110%;
    }

      @media only screen and (min-width: 237.5em)
    {
        font-size: 120%;
    }
  }

  :global(a) {
    text-decoration: none;
  }
</style>
