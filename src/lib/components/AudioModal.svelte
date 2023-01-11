<script lang="ts">
  import { fade } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
  import { MUSIC_PLAYER } from '../stores/music-player';

  let isOpen = true;

  const closeModal = () => isOpen = false;

  const allowAudio = () => {
    closeModal();
    $MUSIC_PLAYER.play();
  }

  const denyAudio = () => {
    closeModal();
  }
</script>

{#if isOpen}
  <div class="modal-wrapper" out:fade={{ duration: 300, easing: quintOut }}>
    <div class="modal">
      <h1>For the full experience, please allow sound to be played!</h1>
      <div class="buttons">
        <button class="button allow" on:click={allowAudio}>it's ok!!</button>
        <button class="button deny" on:click={denyAudio}>no</button>
      </div>
    </div>
  </div>
{/if}

<style lang="sass">
  .modal-wrapper
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%
    background-color: rgba(#2c2f33, .05)
    backdrop-filter: blur(1rem)
    display: flex
    justify-content: center
    align-items: center
    padding: 1.5rem

  .modal
    max-width: 37.5rem
    display: flex
    flex-direction: column
    gap: 1.5rem
    padding: 3rem 1.5rem
    border-radius: 1rem
    border: 1px solid #fff
    background-color: rgba(#fff, .2)

    h1
      font-size: 2.5rem
      font-style: italic

    .buttons
      display: flex
      gap: .5rem

      .button
        font-size: 1rem
        padding: .5rem 1rem
        border: none
        border-radius: .25rem
        cursor: pointer

        &.deny
          background-color: rgba(#fff, .1)
          border: 1px solid #fff
          color: #fff
</style>