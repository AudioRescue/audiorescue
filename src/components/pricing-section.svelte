<script lang="ts">
  import PlanCard from './plan-card.svelte';
  import ToggleSwitch from './toggle-switch.svelte';
  import { writable } from 'svelte/store';

  interface Plan {
    name: string;
    price: number;
    features: string[];
    highlighted?: boolean;
  }

  let interval = 'monthly';

  const plans: Plan[] = [
    { name: 'Freelance', price: 5, features: ['50GB file storage', 'File manager', 'Upgrade any time'] },
    { name: 'Teams', price: 20, features: ['200GB file storage', 'Collaboration mode', 'Up to 10 users', 'Trello integration'], highlighted: true },
    { name: 'Enterprise', price: 80, features: ['Unlimited file storage', 'Admin dashboard', 'Unlimited users', 'All features'] },
  ];

  function handleToggle(event: CustomEvent) {
    interval = event.detail;
    // Additional logic to adjust prices based on interval can be added here
  }
</script>

<ToggleSwitch on:toggle={handleToggle} />

<div class="pricing-section">
  {#each plans as plan}
    <PlanCard {...plan} />
  {/each}
</div>

<style>
  .pricing-section {
    display: flex;
    justify-content: center;
    padding: 50px;
    gap: 20px;
  }
</style>

