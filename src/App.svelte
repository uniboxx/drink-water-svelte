<script lang="ts">
  import Cup from './lib/Cup.svelte';

  const numCups = 8;
  const goal = Math.floor(numCups * 0.25 * 10) / 10;

  let fullCupsNum = $state(0);
  let remaining = $derived(goal - fullCupsNum * 0.25);
</script>

<h1>Drink Water</h1>
<h3>{`Goal: ${goal} Liters`}</h3>
<div class="cup">
  <div class="remained" id="remained">
    <span id="liters">{`${remaining}L`}</span><small>Remained </small>
  </div>
  <div
    class="percentage"
    id="percentage"
    style={`height: ${fullCupsNum * 10}%;`}>
  </div>
</div>
<p class="text">Select how many glasses of water that you have drank</p>
<div class="cups">
  {#each new Array(numCups) as cup, idx (idx)}
    <Cup id={idx + 1} bind:fullCupsNum />
  {/each}
</div>

<style lang="scss">
  h3 {
    font-weight: 400;
    margin: 10px 0;
  }

  .text {
    text-align: center;
    margin: 0 0 20px;
  }
  .cups {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    width: 280px;
  }
</style>
