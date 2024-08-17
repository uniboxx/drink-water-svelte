<script lang="ts">
  import Cup from './lib/Cup.svelte';
</script>

<h1>Drink Water</h1>
<h3>Goal: 2 Liters</h3>
<div class="cup">
  <div class="remained" id="remained">
    <span id="liters">2L</span><small>Remained </small>
  </div>
  <div class="percentage" id="percentage"></div>
</div>
<p class="text">Select how many glasses of water that you have drank</p>
<div class="cups">
  {#each new Array(8) as cup, idx (idx)}
    <Cup />
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
