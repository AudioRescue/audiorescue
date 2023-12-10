<script lang="ts">
  import { onMount } from "svelte";
  import Link from "./link.svelte";
  let lastScrollY: number = 0;
  let navbarVisible: boolean = true;
  export let navColor = "transparent";

  const handleScroll = () => {
    const currentScrollY = window.scrollY;
    navbarVisible = currentScrollY < lastScrollY || currentScrollY <= 0;
    lastScrollY = currentScrollY;
  };

  onMount(() => {
    const intersectionObserver = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (!entry.isIntersecting) {
          navColor = "transparent";
        } else {
          navColor = "var(--color-nav)";
        }
      });
    });
    const target = document.querySelector("#features");
    intersectionObserver.observe(target!);
    window.addEventListener("scroll", handleScroll);

    return () => {
      window.removeEventListener("scroll", handleScroll);
      intersectionObserver.disconnect();
    };
  });
</script>

<nav style="background-color: {navColor}" class="navbar" class:hidden={!navbarVisible}>
  <div class="nav-content">
    <div class="nav-brand">
      <div
        style="width:50px;height:50px;overflow: hidden;border-radius:50px;background:#042539;padding:2px"
      >
        <img src="logo.png" alt="logo" style="width:100%;height:100%;object-fit:cover;" />
      </div>
      <div>AudioRescue</div>
    </div>
    <ul class="nav-links">
      <li><Link href="#services">Services</Link></li>
      <li><Link href="#about">About</Link></li>
      <li><Link href="#contact">Contact</Link></li>
    </ul>
  </div>
</nav>

<style>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    padding: 1rem;
    transition-property: transform, background-color;
    transition-duration: 0.3s;
    transition-timing-function: ease-in-out;
    z-index: 10;
    color: white;
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.1rem;
  }

  .hidden {
    transform: translateY(-100%);
  }

  .nav-content {
    max-width: 1200px;
    margin: auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-brand {
    font-size: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .nav-links {
    list-style: none;
    display: flex;
    gap: 0.5rem;
    margin: 0;
    padding: 0;
  }

  .nav-links li {
    padding: 0.5rem;
  }

  @media (max-width: 768px) {
    .nav-content {
      flex-direction: column;
    }
  }
</style>
