<script lang="ts">
  import Button from "./button.svelte";
</script>

<div id="hero" class="hero">
  <div class="hero-container">
    <h1 class="hero-headline">
      <div style="width: 100%; max-width: 90vw; margin: auto;">
        <!-- <svg -->
        <!--   viewBox="0 0 770 120" -->
        <!--   preserveAspectRatio="xMidYMid meet" -->
        <!--   xmlns="http://www.w3.org/2000/svg" -->
        <!-- > -->
        <!--   <path id="curvePath" fill="none" d="M 80,120 Q 330,50 690,120" /> -->
        <!--   <text -->
        <!--     fill="currentColor" -->
        <!--     font-size="80" -->
        <!--     font-weight="600" -->
        <!--     letter-spacing="2rem" -->
        <!--     font-family="Poppins" -->
        <!--   > -->
        <!--     <textPath xlink:href="#curvePath">Spotless</textPath> -->
        <!--   </text> -->
        <!-- </svg> -->
        <div class="hero-headline__first">Spotless</div>

        <div
          style="margin-bottom: 1rem; margin-top: -1rem; display:flex; justify-content: center; align-items: center;"
          class="hero-headline__second"
        >
          Audio
        </div>
        <div class="hero-headline__third">
          For <span>Spot-On</span> Impressions.
        </div>
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
    height: 95vh;
    background: radial-gradient(
        58.22% 36.38% at 89.87% 83.78%,
        rgba(76, 32, 80, 0.4) 0,
        rgba(0, 0, 0, 0) 100%
      ),
      radial-gradient(
        83.73% 63.48% at 50.13% 98.05%,
        rgba(41, 79, 99, 0.8) 0,
        rgba(0, 0, 0, 0) 100%
      ),
      #000034;
    background-size: cover;
    color: white;
    text-align: center;
    padding: 2rem;
    max-width: 100%;
    overflow: hidden;
  }

  .hero-container {
    width: clamp(450px, 85vw, 800px);
    height: 20rem;
    padding: 2rem;
    border-radius: 20px;
    text-transform: uppercase;
    letter-spacing: 0.5rem;
    font: 500 clamp(14px, 2vw, 1rem) "Poppins", sans-serif;
  }

  .hero-headline__first {
    max-width: 100%;
    font-size: clamp(1.5rem, 16vw, 10rem);
  }
  .hero-headline__second::before {
    content: "";
    display: inline-block;
    width: 6rem;
    height: 3px;
    background: white;
    position: relative;
    left: -0.5rem;
    border-radius: 10px;
  }
  .hero-headline__second::after {
    content: "";
    display: inline-block;
    width: 6rem;
    height: 3px;
    background: white;
    position: relative;
    border-radius: 10px;
  }
  .hero-headline__third {
    font-family: "Dosis", sans-serif;
  }
  span {
    position: relative;
  }

  span::before {
    content: "";
    position: absolute;
    height: 2px;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #3cefff;
    transform-origin: bottom left;
    transform: scaleX(1);
    transition: transform 0.3s ease-in-out;
  }

  span:hover::before {
    transform: scaleX(0);
    transform-origin: bottom right;
  }
</style>
