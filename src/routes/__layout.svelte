<!-- ===================
COMPONENT JS - BASIC 
  [TypeScript Written]
=================== -->

<script lang="ts">
  import { amp, browser, dev, mode, prerendering } from '$app/env';

  import { userBetarenaSettings } from '$lib/store/user-settings';
  import { fixtureVote } from '$lib/store/vote_fixture';

  import '../app.css';

  // ... kickstart the .localStorage();
  // ... kickstart offline-badge on info;
  if (browser) {
      fixtureVote.useLocalStorage();
      userBetarenaSettings.useLocalStorage();
  }
</script>

<!-- ===================
COMPONENT HTML
=================== -->

<main class:dark-background={$userBetarenaSettings.theme == 'Dark'}>
  <slot />
</main>

<!-- ===================
	COMPONENT STYLE
=================== -->

<style>
	main {
    /* 
    so nothing exceeds the main-page-boundries */
    position: relative;
    z-index: 0;
    margin: 0 auto;
    width: 100%;
    /* overflow: hidden; */
    /* 
    make sure the initial page height is always full-device-height as a minumim */
    /* min-height: 100vh; */
  }
</style>
