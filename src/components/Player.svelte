<script lang="ts">
  import PauseIcon from '../icons/pause.svg';
  import PlayIcon from '../icons/play.svg';

  export let src: string;
  let audio, paused;

  const toggleAudio = () => {
    if (audio.paused) audio.play();
    else audio.pause();
  };
</script>

<audio src={src} bind:this={audio} volume={0.5} autoplay bind:paused />
<button on:click={toggleAudio}>
  {#if paused}
  <PlayIcon height={24} width={24} viewBox="0 0 50 50" fill="rgba(0, 0, 0, 0.5)" />
  {:else} <PauseIcon height={24} width={24} viewBox="0 0 50 50" fill="rgba(0, 0, 0, 0.5)" />
  {/if}
</button>

<style>
  button {
    border: 0;
    background-color: transparent;
    width: 40px;
    height: 40px;
    outline: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  button:hover {
    cursor: pointer;
  }
</style>