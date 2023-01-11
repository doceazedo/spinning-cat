<script lang="ts">
  import AudioToggle from "./AudioToggle.svelte";
</script>

<footer class="footer">
  <p>Made with <a href="https://threlte.xyz" target="blank_">Threlte</a></p>
  <p>3D model by <a href="https://sketchfab.com/alwayshasbean" target="blank_">alwayshasbean</a> (CC BY 4.0)</p>
  <p>Created by <a href="https://github.com/doceazedo/spinning-cat" target="blank_">DoceAzedo</a></p>
  <AudioToggle />
</footer>

<style lang="sass">
  .footer
    position: absolute
    bottom: 0
    display: flex
    justify-content: center
    text-align: center
    width: 100%
    padding: 1rem
    gap: 1rem

    p
      color: rgba(#fff, .85)

      a
        font-style: italic
        color: inherit

        &:hover
          color: #fff

  @media screen and (max-width: 768px)
    .footer
      flex-direction: column
      align-items: center
      gap: .25rem
</style>