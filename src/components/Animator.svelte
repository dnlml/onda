<script lang="ts">
  import Letter from './Letter.svelte';
  import Static from './Static.svelte';

  $: letter = '';

  const setLetter = (value: string) => {
    letter = value;
  };
</script>

<div class="wrapper">
  <div class="container">
    <span class="component-container">
      <Static {setLetter} />
    </span>
    <Letter {letter} />
  </div>
</div>

<style>
  .wrapper {
    position: relative;
    background: linear-gradient(45deg, hsla(178, 75%, 75%, 1) 0%, hsla(278, 75%, 75%, 1) 100%);
    height: 100vh;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .container {
    text-align: center;
  }

  .component-container {
    position: relative;
    z-index: 10;
  }
</style>
