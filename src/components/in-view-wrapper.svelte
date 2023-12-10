<script lang="ts">
  import { onMount } from "svelte";
  import { inview } from "svelte-inview";
  import type { ObserverEventDetails, Options } from "svelte-inview";
  import { writable, derived } from "svelte/store";

  export let animationType: "fadeIn" | "slideIn" | "scaleIn" = "fadeIn";
  export let options: Options = {
    rootMargin: "-200px",
    unobserveOnEnter: true
  };

  let section: HTMLDivElement;
  let inView = writable(false);
  export let transitionDuration = 250;
  export let from: "left" | "right" = "left";
  export let delay = 0;
  export let className = "";

  onMount(() => {
    section.style.transition = `all ${transitionDuration}ms`;
  });

  // Derived store to handle different animation types
  const animationStyle = derived(inView, ($inView) => {
    console.log($inView, animationType);
    switch (animationType) {
      case "fadeIn":
        return $inView ? "opacity: 1;" : "opacity: 0;";
      case "slideIn":
        return $inView
          ? `opacity: 1; transform: translateX(1);` // translateX(0) messes up z-index
          : `opacity: 0; transform: translateX(${from === "left" ? "-20px" : "20px"});`;
      case "scaleIn":
        // Define scaleIn animation style
        break;
      default:
        return "";
    }
  });

  const handleChange = ({ detail }: CustomEvent<ObserverEventDetails>) => {
    console.log(detail);
    setTimeout(() => {
      inView.set(detail.inView);
    }, delay);
  };
</script>

<noscript>
  <style>
    div {
      opacity: 1 !important;
      transform: none !important;
    }
  </style>
</noscript>

<div
  class={className}
  style={$animationStyle}
  bind:this={section}
  use:inview={options}
  on:inview_change={handleChange}
>
  <slot />
</div>

<style>
  div {
    position: relative;
    transition: all 550ms;
  }
</style>
