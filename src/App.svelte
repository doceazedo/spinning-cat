<script lang="ts">
  import { Canvas } from '@threlte/core';
  import SpinningCat from './lib/scenes/SpinningCat.svelte';
  import Header from './lib/components/Header.svelte';
  import Footer from './lib/components/Footer.svelte';
  import AudioModal from './lib/components/AudioModal.svelte';
</script>

<Canvas>
  <SpinningCat />
</Canvas>

<Header />
<Footer />
<AudioModal />