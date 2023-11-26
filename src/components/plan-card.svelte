<script lang="ts">
  import Button from "./button.svelte";

  export let name: string;
  export let price: number;
  export let features: string[];
  export let highlighted: boolean = false;
</script>

<article class="plan-card {highlighted ? 'highlighted' : ''}">
  <h2>{name}</h2>
  <p class="price">${price}</p>
  <ul>
    {#each features as feature}
      <li>{feature}</li>
    {/each}
  </ul>
  <Button as="a">Get started</Button>
</article>

<style>
  .plan-card {
    border: 1px solid #ccc;
    border-radius: 10px;
    padding: 20px;
    margin: 10px;
    text-align: center;

  }
  .plan-card.highlighted {
    border-color: #007bff;
    box-shadow: 0 2px 10px rgba(0, 123, 255, 0.2);
  }
  .price {
    font-size: 2em;
    color: #333;
  }
</style>
