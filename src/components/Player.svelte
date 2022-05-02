<script lang="ts">
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
  <img 
    src={`/assets/common/${isPlaying ? 'pause' : 'play'}.svg`} 
    alt={`${isPlaying ? 'pause' : 'play'} icon`}
    width={24}
    height={24}
  />
</button>

<style>
  button {
    border: 0;
    background-color: transparent;
    width: 40px;
    height: 40px;
    outline: none;
    margin: 0;
    padding: 0;
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }

  button:hover {
    cursor: pointer;
  }

  img {
    fill: gray;
  }
</style>