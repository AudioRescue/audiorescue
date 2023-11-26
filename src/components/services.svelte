<script lang="ts">
  // Import any icons or images if necessary
</script>

<div id="services"
	class="services-section">
  <h2 class="services-title">Our Digital Audio Repair Services</h2>
  <div class="services-list">
    <div class="service-item">
      <div class="service-icon">🔊</div>
      <h3 class="service-title">Audio File Repair</h3>
      <p class="service-description">
        Expert solutions for corrupted or damaged audio files, ensuring clarity and integrity.
      </p>
    </div>

    <div class="service-item">
      <div class="service-icon">🎚️</div>
      <h3 class="service-title">Sound Quality Enhancement</h3>
      <p class="service-description">
        Enhance the fidelity and quality of your audio tracks for a superior listening experience.
      </p>
    </div>

    <!-- Add more service items as needed -->
  </div>
</div>

<style>
  .services-section {
    padding: 4rem 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .services-title {
    font-size: 2.5rem;
    margin-bottom: 2rem;
    text-align: center;
  }

  .services-list {
    display: flex;
    width: 100%;
    max-width: 1200px;
    overflow-x: scroll;
    scroll-snap-type: x mandatory;
  }

  .service-item {
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    text-align: center;
    min-width: 300px;
    scroll-snap-align: center;
  }

  .service-icon {
    font-size: 3rem;
    margin-bottom: 1rem;
    color: #3498db; /* Icon color */
  }

  .service-title {
    font-size: 1.8rem;
    margin-bottom: 1rem;
  }

  .service-description {
    font-size: 1.1rem;
  }
</style>
