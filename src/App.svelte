<script lang="ts">
	import { fly } from 'svelte/transition';

	const song = new Audio('/assets/songs/drunken-sailor.mp3');
	song.play();
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet">
	<link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet">
</svelte:head>

<main>
	<div class="letter" transition:fly={{ y: -40, duration: 1000 }}>
		<img src="/assets/wax-seal.png" class="wax-seal" width={70} alt="Wax seal" />
		<h1>VLRN</h1>
		<p>Alas! Brave adventurer, </p>
		<p>
			You have met a sad fate. But do not despair, for the gods will bring you 
			back into the world in exchange for a small sacrifice. Simply copy the 
			URL and join our server at Veloren!
		</p>
		<p>
			Cheers, <br />
			hnrq
		</p>
		<input value="vlrn.hnrq.dev" disabled />
	</div>
</main>

<style>

	main {
		text-align: center;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100%;
	}

	input {
		margin-top: 16px;
		border: none;
		background: rgba(0, 0, 0, 0.17);
		border-radius: 0;
	}

	input:disabled {
		color: black;
	}

	.letter {
		max-width: 328px;
		background: #FFFCE4;
		box-shadow: 0px 0px 0px 4px #000000;
		padding: 16px 24px;
		padding-top: 0;
		padding-bottom: 48px;
		display: flex;
		flex-direction: column;

	}

	.wax-seal {
		transform: translateY(-35%);
		-webkit-filter: drop-shadow(0px 3px 0px #000);
    filter: drop-shadow(0px 3px 0px #000);
		align-self: center;
	}

	h1 {
		text-align: left;
		font-family: 'Press Start 2P', cursive;
		color: #4C2A12;
		text-shadow: -2px 2px #f4912f;
		margin-top: -8px;
	}

	p {
		text-align: justify;
		margin: 8px 0;
	}
</style>