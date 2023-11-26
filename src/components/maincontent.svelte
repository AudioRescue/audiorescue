<script>
  // Import icons if they are SVG components
  // import IconOne from './IconOne.svelte';
  // import IconTwo from './IconTwo.svelte';
  // import IconThree from './IconThree.svelte';
  // import IconFour from './IconFour.svelte';
</script>

<div class="features-container">
  <div class="feature-card">
    <div class="feature-icon">
      <!-- Replace with actual icon component for Precision Repair -->
      <!-- <PrecisionRepairIcon /> -->
    </div>
    <div class="feature-title">Background Noise Removal</div>
    <div class="feature-text">
      Eliminate distracting background noises from your recordings. Whether it’s traffic, hums, or
      ambient chatter, our advanced noise removal technology ensures your content captures only what
      you intended, delivering pristine, focused audio to your audience.
    </div>
  </div>

  <div class="feature-card">
    <div class="feature-icon" />
    <div class="feature-title">Audio Mixing</div>
    <div class="feature-text">
      Bring balance and depth to your audio tracks. Our expert mixing services skillfully adjust
      levels, EQ, and effects, ensuring each element of your soundtrack coexists in perfect harmony.
      Ideal for podcasts, music, and multimedia projects seeking a professional touch.
    </div>
  </div>

  <div class="feature-card">
    <div class="feature-icon">
      <!-- Replace with actual icon component for Customer Service -->
      <!-- <CustomerServiceIcon /> -->
    </div>
    <div class="feature-title">Volume Leveling</div>
    <div class="feature-text">
      Achieve uniform loudness across your content for a smooth, professional listening experience.
      Our volume leveling techniques prevent abrupt changes in sound, providing a comfortable and
      engaging auditory journey for your audience.
    </div>
  </div>

  <div class="feature-card">
    <div class="feature-icon">
      <!-- Replace with actual icon component for Customer Service -->
      <!-- <CustomerServiceIcon /> -->
    </div>
    <div class="feature-title">Audio Restoration</div>
    <div class="feature-text">
      Restore old or damaged recordings to their former glory. Our audio restoration service
      meticulously reduces noise, clicks, and distortions, breathing new life into vintage audio or
      salvaging imperfect recordings.
    </div>
  </div>
</div>

<style>
  .features-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    justify-content: center;
  }

  .feature-card {
    border-radius: 8px;
    padding: 0.5rem;
    text-align: center;
    transition: box-shadow 0.3s ease-in-out;
    width: clamp(300px, 100%, 400px);
  }

  .feature-card:hover {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }

  .feature-icon {
    /* Placeholder for the icon styles */
    margin-bottom: 1rem;
  }

  .feature-title {
    margin-bottom: 1rem;
    font-size: 1.25rem;
    font-weight: 600;
  }

  .feature-text {
  }
</style>
