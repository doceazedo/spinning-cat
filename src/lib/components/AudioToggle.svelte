<script lang="ts">
  import { onMount } from 'svelte';
  import { MUSIC_PLAYER } from '../stores/music-player';
  
  const volume = .25;
  let muted = true;

  onMount(() => {
    $MUSIC_PLAYER = new Audio('/audio/funky_town.mp3');
    $MUSIC_PLAYER.volume = volume;
    $MUSIC_PLAYER.loop = true;

    $MUSIC_PLAYER.addEventListener('play', onPlay);
  });

  const toggleMute = () => {
    muted = !muted;
    $MUSIC_PLAYER.volume = muted ? 0 : volume;
    $MUSIC_PLAYER.play();
  }

  const onPlay = () => muted = false;
</script>

<button class="button" on:click={toggleMute}>{muted ? '🔇' : '🔊'}</button>

<style lang="sass">
  .button
    width: 1.5rem
    height: 1.5rem
    margin: 0
    padding: 0
    background-color: rgba(#fff, .1)
    border-radius: 50%
    border: none
    cursor: pointer
</style>