<script lang="ts">
  const name = 'HYPERLAB';

  export let setLetter: (letter: string) => void;
</script>

{#each name as letter}
  <span
    on:mouseenter={() => {
      setLetter(letter);
    }}
    on:mouseleave={() => {
      setLetter('');
    }}>{letter}</span
  >
{/each}

<style>
  span {
    display: inline-block;
    font-weight: 200;
    font-stretch: semi-expanded;
    text-transform: uppercase;
    font-size: 10vw;
    transition: all 1s cubic-bezier(0, 0.72, 0.3, 0.81);
    cursor: cell;
  }

  span:hover {
    font-weight: 800;
    font-stretch: expanded;
    transform: scaleX(1.5);
  }

  span:hover + span {
    transition-delay: 0.1s;
    font-weight: 400;
  }
</style>
