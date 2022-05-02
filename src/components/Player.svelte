<script lang="ts">
  import PauseIcon from '../icons/pause.svg';
  import PlayIcon from '../icons/play.svg';

  export let src: string;
  let audio = new Audio(src);
  let isPlaying: boolean = false;
  audio.volume = 0.5;

  const toggleAudio = () => {
    if (audio.paused) {
      audio.play();
      isPlaying = true;
    } else {
      audio.pause();
      isPlaying = false;
    }
  };
</script>

<button on:click={toggleAudio}>
  {#if isPlaying}
  <PauseIcon height={24} width={24} viewBox="0 0 50 50" fill="rgba(0, 0, 0, 0.5)" />
  {:else} <PlayIcon height={24} width={24} viewBox="0 0 50 50" fill="rgba(0, 0, 0, 0.5)" />
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