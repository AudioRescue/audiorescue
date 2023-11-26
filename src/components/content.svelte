<script lang="ts">
  import { fade, fly } from "svelte/transition";
  import { inview } from "svelte-inview";
  import type { ObserverEventDetails, Options } from "svelte-inview";
  export let title: string;
  export let text1: string;
  export let text2: string = "";
  export let image: string;
  export let checkmarks: string[] = [];
  export let reverse: boolean = false;

  const parseBoldText = (text: string) => {
    return text;
  };
  let isInView = false;
  const options: Options = {
    rootMargin: "-350px",
    unobserveOnEnter: true
  };

  const handleChange = ({ detail }: CustomEvent<ObserverEventDetails>) => {
    isInView = detail.inView;
    console.log(isInView);
  };
</script>

<div class="container" use:inview={options} on:inview_change={handleChange}>
  <section class="content-section">
    <div class="inner-container">
      <div class="flex-container {reverse ? 'reverse' : ''}">
          <div in:fly={{ y: -20, duration: 800 }} class="image-container">
            <div class="image-wrapper">
              <img src={image} alt={image.replace(/.*\//, "")} />
            </div>
          </div>
          <div in:fade={{ duration: 1000, delay: 300 }} class="text-container">
            <div class="text-block {reverse ? 'text-block-reverse' : ''}">
              <h2>{title}</h2>
              <p class="paragraph">
                {parseBoldText(text1)}
              </p>
              {#if text2}
                <p>{parseBoldText(text2)}</p>
              {/if}
            </div>
          </div>
      </div>
    </div>
  </section>

</div>

<style>
  /* Structural Styles */
  .container {
    max-width: 100%;
    margin: 6rem auto;
    padding: 0 1.5rem;
  }
  .content-section {
    margin-bottom: 8rem;
  }
  .inner-container {
    position: relative;
    max-width: 100%;
    margin: auto;
    text-align: center;
  }
  .flex-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }
  .flex-container.reverse {
    flex-direction: column-reverse;
  }
  .image-container,
  .text-container {
    width: 100%;
  }

  /* Spacing Styles */
  .text-block {
    padding: 3rem 1.5rem;
    margin-bottom: 3rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(20px);
  }
  .text-block-reverse {
    margin-right: -3.5rem;
  }

  /* Typography Styles */
  h2 {
    margin-bottom: 1.5rem;
    font-size: 1.875rem; /* 3xl */
    font-weight: bold;
  }

  /* Other Styles */
  .image-wrapper {
    height: 30rem;
    border-radius: 0.5rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    position: relative;
  }
  .image-wrapper img {
    border-radius: 0.5rem;
    object-fit: cover;
    object-position: center;
  }

  /* Responsive Styles */
  @media (min-width: 1024px) {
    /* lg breakpoint */
    .flex-container {
      flex-direction: row;
    }
    .flex-container.reverse {
      flex-direction: row-reverse;
    }
    .image-container,
    .text-container {
      width: 50%;
    }
    .inner-container {
      text-align: left;
    }
    .text-block {
      padding: 3rem 3rem;
    }
    .text-block-reverse {
      margin-left: -3.5rem;
    }
  }
</style>
