<script lang="ts">
  import { onMount } from "svelte";
  export let color:
    | "primary"
    | "secondary"
    | "accent-primary"
    | "accent-secondary"
    | "accent-tertiary" = "primary";

  let componentElement: HTMLDivElement;
  export let style: string = "";

  onMount(() => {
    const cursorElement: HTMLDivElement = componentElement.querySelector(".cursor-gradient")!;

    const handleMouseMove = (e: MouseEvent) => {
      const rect = componentElement.getBoundingClientRect();
      const x = e.clientX - rect.left; //x position within the element.
      const y = e.clientY - rect.top; //y position within the element.

      cursorElement.style.left = `${x}px`;
      cursorElement.style.top = `${y}px`;
      cursorElement.style.width = `1000px`;
      cursorElement.style.height = `500px`;
      componentElement.style.transform = `perspective(1000px) rotateY(${
        (x / rect.width) * 10 - 5
      }deg) rotateX(${(y / rect.height) * -10 + 5}deg)`;
    };

    componentElement.addEventListener("mousemove", handleMouseMove);

    componentElement.addEventListener("mouseout", () => {
      cursorElement.style.width = `0`;
      cursorElement.style.height = `0`;
      componentElement.style.transform = `none`;
    });
  });
</script>

<div
  bind:this={componentElement}
  class="gradient-component"
  style={`outline-color: rgba(var(--color-${color}), 0.25); ${style}`}
>
  <div
    class="cursor-gradient"
    style={`background: radial-gradient(
      circle,
       rgba(var(--color-${color}), 0.5) 0%,
      rgba(255, 255, 255, 0) 70%
    );
    `}
  />
  <slot />
</div>

<style>
  .gradient-component {
    position: relative;
    overflow: hidden;
    border-radius: 20px;
    padding: 1rem;
    outline: 2px solid rgba(100, 100, 100, 0.25);
    z-index: 1;
  }
  .cursor-gradient {
    position: absolute;
    pointer-events: none;
    border-radius: 50%;
    background: radial-gradient(
      circle,
      rgba(var(--color-primary), 0.7) 0%,
      rgba(255, 255, 255, 0) 70%
    );
    transition: width 0.2s ease-in-out, height 0.2s ease-in-out;
    width: 0;
    height: 0;
    transform: translate(-50%, -50%);
    z-index: -1;
  }
</style>
