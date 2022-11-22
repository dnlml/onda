<script lang="ts">
  export let letter = '';
  let currentLetter: string;

  $: if (letter && currentLetter !== letter) {
    currentLetter = letter;
    setTimeout(() => {
      letter = '';
    });
    setTimeout(() => {
      letter = currentLetter;
    }, 20);
  }
</script>

<div class="bg-letter" class:animate={letter !== ''}>
  {letter}
</div>

<style>
  .bg-letter {
    position: absolute;
    display: flex;
    right: 0;
    bottom: 0;
    font-size: 200vh;
    font-stretch: expanded;
    font-weight: 900;
    line-height: 0.2;
    color: hsla(278, 75%, 75%, 1);
  }

  .animate {
    animation: 2s midi;
  }

  @keyframes midi {
    0% {
      opacity: 0.45;
      filter: blur(50px);
    }
    100% {
      opacity: 1;
      filter: blur(0);
    }
  }
</style>
