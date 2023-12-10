<script lang="ts">
  export let href: string;
  export let className: string = "";
  export let style: string = "";
</script>

<a {href} class={className} {style}>
  <slot />
</a>

<style>
  a {
    position: relative;
    text-decoration: none;
    color: white;
  }

  a::before {
    content: "";
    position: absolute;
    height: 2px;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgb(var(--color-primary));
    transform-origin: bottom right;
    transform: scaleX(0);
    transition: transform 0.3s ease-in-out;
  }

  a:hover::before {
    transform: scaleX(1);
    transform-origin: bottom left;
  }
</style>
