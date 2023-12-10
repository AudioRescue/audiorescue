<script lang="ts">
  import Feature from "./feature.svelte";
  import InViewWrapper from "./in-view-wrapper.svelte";
</script>

  <InViewWrapper
    delay={100}
    from="left"
    transitionDuration={2000}
    options={{ rootMargin: "-100px", unobserveOnEnter: true }}>
<div id="features" class="features-container">
  <InViewWrapper animationType="fadeIn" delay={100} >
    <Feature
      color="primary"
      title="Background **N̵̪̙̆̄o̷̧͛i̵̟̅̓s̶̝̻͋̂ę̷͕̈ &nbsp;Removal**"
      text="Eliminate distracting background noises from your recordings. Whether it’s traffic, hums, or ambient chatter, our advanced noise removal technology ensures your content captures only what you intended, delivering pristine, focused audio to your audience."
    >
      <svg
        fill="none"
        stroke-width="2"
        xmlns="http://www.w3.org/2000/svg"
        class="icon icon-tabler icon-tabler-wave-square"
        width="100%"
        height="100%"
        viewBox="0 0 24 24"
        stroke="currentColor"
        stroke-linecap="round"
        stroke-linejoin="round"
        style="overflow: visible; color: currentcolor;"
        ><path stroke="none" d="M0 0h24v24H0z" fill="none" /><path d="M3 12h5v8h4v-16h4v8h5" /></svg
      >
    </Feature>
  </InViewWrapper>

  <InViewWrapper
    animationType="fadeIn"
    delay={200}
    options={{ rootMargin: "-100px", unobserveOnEnter: true }}
  >
    <Feature
      color="secondary"
      title="Audio **Mixing**"
      text="Bring balance and depth to your audio tracks. Our expert mixing services skillfully adjust levels, EQ, and effects, ensuring each element of your soundtrack coexists in perfect harmony. Ideal for podcasts, music, and multimedia projects seeking a professional touch."
    >
      <svg
        fill="currentColor"
        stroke-width="0"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 512 512"
        style="overflow: visible; color: currentcolor;"
        ><path
          d="M256 80C149.9 80 62.4 159.4 49.6 262c9.4-3.8 19.6-6 30.4-6 26.5 0 48 21.5 48 48v128c0 26.5-21.5 48-48 48-44.2 0-80-35.8-80-80V288C0 146.6 114.6 32 256 32s256 114.6 256 256v112c0 44.2-35.8 80-80 80-26.5 0-48-21.5-48-48V304c0-26.5 21.5-48 48-48 10.8 0 21 2.1 30.4 6C449.6 159.4 362.1 80 256 80z"
        /></svg
      >
    </Feature>
  </InViewWrapper>

  <InViewWrapper
    animationType="fadeIn"
    delay={200}
    options={{ rootMargin: "-100px", unobserveOnEnter: true }}
  >
    <Feature
      color="accent-primary"
      title="Volume **Leveling**"
      text="Achieve uniform loudness across your content for a smooth, professional listening experience. Our volume leveling techniques prevent abrupt changes in sound, providing a comfortable and engaging auditory journey for your audience."
    >
      <svg
        fill="none"
        stroke-width="2"
        xmlns="http://www.w3.org/2000/svg"
        stroke="currentColor"
        stroke-linecap="round"
        stroke-linejoin="round"
        viewBox="0 0 24 24"
        style="overflow: visible; color: currentcolor;"
        ><path d="M4 21 4 14" /><path d="M4 10 4 3" /><path d="M12 21 12 12" /><path
          d="M12 8 12 3"
        /><path d="M20 21 20 16" /><path d="M20 12 20 3" /><path d="M1 14 7 14" /><path
          d="M9 8 15 8"
        /><path d="M17 16 23 16" /></svg
      >
    </Feature>
  </InViewWrapper>

  <InViewWrapper
    animationType="fadeIn"
    delay={200}
    options={{ rootMargin: "-100px", unobserveOnEnter: true }}
  >
    <Feature
      color="accent-secondary"
      title="Audio **Restoration**"
      text="Restore old or damaged recordings to their former glory. Our audio restoration service meticulously reduces noise, clicks, and distortions, breathing new life into vintage audio or salvaging imperfect recordings."
    >
      <svg
        fill="currentColor"
        stroke-width="0"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 576 512"
        style="overflow: visible; color: currentcolor;"
        ><path
          d="M234.7 42.7 197 56.8c-3 1.1-5 4-5 7.2s2 6.1 5 7.2l37.7 14.1 14.1 37.7c1.1 3 4 5 7.2 5s6.1-2 7.2-5l14.1-37.7L315 71.2c3-1.1 5-4 5-7.2s-2-6.1-5-7.2l-37.7-14.1L263.2 5c-1.1-3-4-5-7.2-5s-6.1 2-7.2 5l-14.1 37.7zM46.1 395.4c-18.7 18.7-18.7 49.1 0 67.9l34.6 34.6c18.7 18.7 49.1 18.7 67.9 0l381.3-381.4c18.7-18.7 18.7-49.1 0-67.9l-34.6-34.5c-18.7-18.7-49.1-18.7-67.9 0L46.1 395.4zM484.6 82.6l-105 105-23.3-23.3 105-105 23.3 23.3zM7.5 117.2C3 118.9 0 123.2 0 128s3 9.1 7.5 10.8L64 160l21.2 56.5c1.7 4.5 6 7.5 10.8 7.5s9.1-3 10.8-7.5L128 160l56.5-21.2c4.5-1.7 7.5-6 7.5-10.8s-3-9.1-7.5-10.8L128 96l-21.2-56.5c-1.7-4.5-6-7.5-10.8-7.5s-9.1 3-10.8 7.5L64 96 7.5 117.2zm352 256c-4.5 1.7-7.5 6-7.5 10.8s3 9.1 7.5 10.8L416 416l21.2 56.5c1.7 4.5 6 7.5 10.8 7.5s9.1-3 10.8-7.5L480 416l56.5-21.2c4.5-1.7 7.5-6 7.5-10.8s-3-9.1-7.5-10.8L480 352l-21.2-56.5c-1.7-4.5-6-7.5-10.8-7.5s-9.1 3-10.8 7.5L416 352l-56.5 21.2z"
        /></svg
      >
    </Feature>
  </InViewWrapper>
</div>
  </InViewWrapper>

<style>
  .features-container {
    position: relative;
    max-width: 1200px;
    margin: 0 auto 10rem;
    padding: 0 2rem;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    justify-content: center;
  }
  svg {
    position: relative;
    z-index: 1;
  }
  @keyframes reveal {
    to {
      stroke-dashoffset: 0;
    }
  }


  .circuit {
    position: absolute;
    top: 4rem;
    left: 0;
    z-index: -1;
    width: 100%;
    height: calc(100% - 8rem);
    display: flex;
    flex-direction: column;
  }

  .circuit svg {
    width: 4rem;
    height: 33.333%;
  }
  .circuit svg path {
    stroke: rgba(var(--color-accent-secondary), 0.5);
    stroke-dasharray: 1000;
    stroke-dashoffset: 1000;
    animation: reveal 3s linear forwards;
  }
</style>
