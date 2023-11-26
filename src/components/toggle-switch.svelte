<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  function toggle(interval: string) {
    dispatch('toggle', interval);
  }
</script>

<div class="toggle-switch">
  <button on:click={() => toggle('monthly')}>Monthly</button>
  <button on:click={() => toggle('yearly')}>Yearly</button>
</div>

<style>
  .toggle-switch button {
    /* Your button styling here */
  }
</style>

