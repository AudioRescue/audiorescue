<script lang="ts">
  import { createEventDispatcher } from "svelte";

  export let disabled: boolean = false;
  export let as: "button" | "a" = "button";
  export let href: string | undefined = undefined;
  export let type: "button" | "submit" | "reset" = "button";
  export let style: string = "";

  const dispatch = createEventDispatcher();

  // Function to handle click events
  function handleClick() {
    if (!disabled) {
      dispatch("click");
    }
  }
</script>

{#if as === "a"}
  <a {style} class="button" aria-disabled={disabled ? "true" : "false"} {href}>
    <slot />
    <svg viewBox="0 0 24 24" width="1.2em" height="1.2em" class="icon"
      ><path
        fill="none"
        stroke="currentColor"
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M5 12h14m-7-7l7 7l-7 7"
      /></svg
    >
  </a>
{:else}
  <button
    {style}
    {type}
    class="button"
    on:click={handleClick}
    {disabled}
    aria-disabled={disabled ? "true" : "false"}
  >
    <slot />
  </button>
{/if}

<style>
  .button {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1rem 2rem;
    font-size: 1rem;
    color: #fff;
    background-color: black;
    border: 1px solid transparent;
    border-radius: 6px;
    cursor: pointer;
    outline: 2px solid transparent;
    transition: background-color 0.2s, box-shadow 0.2s;
    text-transform: uppercase;
    text-decoration: none;
    font-weight: 600;
    z-index: 1;
    position: relative;
    padding: 0.5em 1em;
    border: none;
    overflow: hidden !important;
    transition: color 0.4s ease-in-out;
  }

  .button:hover:not([aria-disabled="true"]) {
    background-color: #1a1a1a;
    outline: 2px solid rgba(var(--color-primary), 0.5);
    color: black;
  }

  .button:active:not([aria-disabled="true"]) {
    box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  }

  .button[aria-disabled="true"] {
    cursor: not-allowed;
  }
  .icon {
    display: inline-block;
    vertical-align: middle;
    fill: none;
    stroke: currentColor;
    stroke-width: 2;
    transition: width 0.2s;
    width: 0px;
  }
  .button:hover .icon {
    width: 1.2em;
  }

  .button::before {
    content: "";
    z-index: -1;
    position: absolute;
    top: 100%;
    right: 100%;
    width: 1.5em;
    height: 1.5em;
    border-radius: 50%;
    background-color: rgb(var(--color-primary));
    transform-origin: center;
    transform: translate3d(50%, -50%, 0) scale3d(0, 0, 0);
    transition: transform 0.3s ease-in-out;
  }

  .button:hover::before {
    transform: translate3d(50%, -50%, 0) scale3d(15, 15, 15);
  }
</style>
