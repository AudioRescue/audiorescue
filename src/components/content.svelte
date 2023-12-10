<script>
  import InViewWrapper from "./in-view-wrapper.svelte";

  export let title = "";
  export let text = "";
  export let imageUrl = "";
  export let altText = "";
  export let reverse = false;
</script>

<div class="container">
  <div class={reverse ? "flex-container reverse" : "flex-container"}>
    <InViewWrapper
      animationType="slideIn"
      delay={100}
      from={reverse ? "right" : "left"}
      transitionDuration={2000}
    >
    <div class={reverse ? "box reverse" : "box"}>
      <div class={reverse ? "text-container reverse" : "text-container"}>
        <h2 class="h2">{title}</h2>
        <div class="p-container">
          <p class="p">{text}</p>
        </div>
      </div>
    </div>
    </InViewWrapper>
    <InViewWrapper
      animationType="slideIn"
      delay={400}
      from={reverse ? "left" : "right"}
      transitionDuration={2000}
      options={{ rootMargin: "-100px", unobserveOnEnter: true }}
    >
      <div class={reverse ? "image-container reverse" : "image-container"}>
        <img src={imageUrl} alt={altText} />
      </div>
    </InViewWrapper>
  </div>
</div>

<style>
  .container {
    max-width: 100%;
    display: flex;
    justify-content: center;
    padding: 0 1rem;
    position: relative;
  }
  .flex-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }
  .text-container {
    position: relative;
    padding: 0.5rem 2rem;
    left: -0.5rem;
    top: 5rem;
    z-index: 1;
    background-color: rgba(var(--color-background), 0.8);
    backdrop-filter: blur(10px);
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.25);
    border-top: 2px solid rgba(var(--color-accent-secondary), 1);
    border-bottom: 2px solid rgba(var(--color-primary), 1);
    background-image: linear-gradient(
        90deg,
        rgba(var(--color-primary), 1),
        rgba(var(--color-accent-secondary), 1)
      ),
      linear-gradient(90deg, rgba(var(--color-primary), 1), rgba(var(--color-accent-secondary), 1));
    background-size: 2px 100%;
    background-position: 100% 0, 100% 0;
    background-repeat: no-repeat;
    border-radius: 0rem 1rem 1rem 0rem;
  }
  .text-container::before {
    content: "";
    position: absolute;
    left: -8px;
    width: 0.5rem;
    height: calc(100% + 2px);
    top: -1px;
    background: linear-gradient(
      45deg,
      rgba(var(--color-primary), 1),
      rgba(var(--color-accent-secondary), 1)
    );
    border-radius: 1rem 0 0 1rem;
  }

  .text-container.reverse {
    left: auto;
    right: -0.5rem;
    border-radius: 1rem 0rem 0rem 1rem;
    border-top: 2px solid rgba(var(--color-primary), 0.8);
    border-bottom: 2px solid rgba(var(--color-accent-secondary), 0.8);
    background-image: linear-gradient(
        90deg,
        rgba(var(--color-accent-secondary), 0.8),
        rgba(var(--color-primary), 0.8)
      ),
      linear-gradient(
        90deg,
        rgba(var(--color-accent-secondary), 0.8),
        rgba(var(--color-primary), 0.8)
      );
    background-size: 2px 100%;
    background-position: 0% 0, 0% 0;
    background-repeat: no-repeat;
  }
  .text-container.reverse::before {
    left: auto;
    right: -6px;
    border-radius: 0 1rem 1rem 0;
  }
  .image-container {
    position: relative;
    border-radius: 1rem;
    overflow: hidden;
    max-height: 400px;
    left: auto;
    right: -0.5rem;
    z-index: 0 !important;
    outline: 2px solid rgba(var(--color-primary), 0.2);
  }
  .image-container::before {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    width: 0.5rem;
    height: 100%;
    background-color: rgb(var(--color-primary));
    border-radius: 0 1rem 1rem 0;
  }
  .image-container.reverse {
    right: auto;
    left: -0.5rem;
  }
  .image-container.reverse::before {
    left: 0;
    right: auto;
    border-radius: 1rem 0 0 1rem;
  }
  .image-container img {
    object-fit: cover;
    object-position: 50% 30%;
    width: 100%;
    height: 100%;
    border-radius: 1rem;
  }
  .p-container {
    position: relative;
  }

  .box:before {
    content: "";
    z-index: -1;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background: linear-gradient(-45deg, rgba(var(--color-primary), 1), rgba(var(--color-accent-secondary), 1));
    transform: translate3d(50px, 20px, 0) scale(0.95);
    filter: blur(20px);
    opacity: 0.2;
    transition: opacity 0.5s, transform 0.5s;
    border-radius: 1rem;
  }
  .box:hover:before {
    opacity: 0.4;
    transform: translate3d(50px, 20px, 0) scale(1);
  }
  .box.reverse:before {
    transform: translate3d(-50px, 20px, 0) scale(0.95);
  }
  .box.reverse:hover:before{
    transform: translate3d(-50px, 20px, 0) scale(1);
  }

  /* 
* Prevents issues when the parent creates a 
* stacking context. (For example, using the transform
* property )
*/
  .box::after {
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

  @media (min-width: 900px) {
    .container {
      margin-bottom: 4rem;
    }
    .flex-container {
      position: relative;
      flex-direction: row;
      max-width: 1000px;
      left: -2.5rem;
    }
    .flex-container.reverse {
      position: relative;
      flex-direction: row-reverse;
      left: 2.5rem;
    }
    .image-container {
      min-width: 500px;
      max-width: 500px;
      right: 0;
    }
    .image-container::before {
      display: none;
    }
    .image-container.reverse {
      left: 0;
    }
    .text-container {
      left: 5rem;
      top: 0;
    }
    .text-container.reverse {
      left: -5rem;
      top: 0;
    }
    .flex-container.reverse {
      flex-direction: row-reverse;
    }
  }
  h2 {
    margin-bottom: 1.5rem;
    background: linear-gradient(
      45deg,
      #fff,
      #fff 45%,
      rgb(var(--color-primary)) 50%,
      #fff 55%,
      #fff
    );
    background-clip: text;
    background-size: 200% 100%;
    -webkit-background-clip: text;
    color: transparent;
    animation: shine 2s linear;
  }
  @keyframes shine {
    0% {
      background-position: -500px;
    }
    100% {
      background-position: 400px;
    }
  }
</style>
