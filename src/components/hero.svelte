<script lang="ts">
  import Button from "./button.svelte";
  import Circles from "./circles.svelte";
</script>

<div id="hero" class="hero">
	<Circles
	 style="position: absolute; top: 0; left: auto; right: auto; bottom: 0; z-index: 0; scale: 0.75;
	 "
		/>
  <div class="hero-container">
    <h1 class="hero-headline">
      <div class="hero-headline__first">Spotless Audio</div>
      <div class="hero-headline__third">
        For <span>Spot-On</span> Impressions.
      </div>
    </h1>
  </div>
  <Button as="a" href="#contact">Try it free</Button>
</div>

<style>
  .hero {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 64rem;
    width: 100%;
    background: radial-gradient(
        58.22% 36.38% at 89.87% 83.78%,
        rgba(71, 37, 100, 0.8) 0,
        rgba(0, 0, 0, 0) 100%
      ),
      radial-gradient(
        83.73% 63.48% at 50.13% 98.05%,
        rgba(94, 71, 24, 0.4) 0,
        rgba(0, 0, 0, 0) 100%
      ),
      rgb(var(--color-background));
    background-size: cover;
    color: white;
    text-align: center;
    max-width: 100%;
    overflow: hidden;
  }


  .hero-container {
    pointer-events: none;
    width: clamp(450px, 85vw, 800px);
    padding: 1rem;
    border-radius: 20px;
    text-transform: uppercase;
    letter-spacing: 0.5rem;
    font: 500 clamp(14px, 2vw, 1rem) "Poppins", sans-serif;
    z-index: 1;
    text-shadow: 0 0 8px rgba(0, 0, 0, 1);
  }

  .hero-headline__first {
    max-width: 100%;
    font-size: clamp(1.5rem, 16vw, 6rem);
    line-height: 1.2;
  }
  .hero-headline__third {
    font-family: "Dosis", sans-serif;
  }

  span {
    position: relative;
    display: inline-block;
    color: white;
    text-shadow: 0 0 8px rgba(0, 0, 0, 1);
  }
  span:before {
    content: "";
    z-index: -1;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background: linear-gradient(
      -45deg,
      rgb(var(--color-primary)) 0%,
      rgb(var(--color-secondary)) 100%
    );
    background-size: 200% 200%;
    transform: translate3d(0px, 10px, 0) scale(0.95);
    filter: blur(20px);
    opacity: 1;
    transition: opacity 0.3s;
    border-radius: inherit;
    animation: gradient 5s ease infinite;
  }
  @media (prefers-reduced-motion: reduce) {
    span:before {
      animation: none;
    }
  }

  /* 
* Prevents issues when the parent creates a 
* stacking context. (For example, using the transform
* property )
*/
  span::after {
    content: "";
    z-index: -1;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background: inherit;
    border-radius: inherit;
  }
  @keyframes gradient {
    0%,
    100% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
  }
</style>
