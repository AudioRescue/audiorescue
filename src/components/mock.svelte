<script lang="ts">
  import { writable } from 'svelte/store';

  const uploadProgress = writable(0);
  let uploading = false;

  function startUploadMock() {
    uploading = true;
    uploadProgress.set(0);

    const interval = setInterval(() => {
      uploadProgress.update(n => {
        if (n >= 100) {
          clearInterval(interval);
          uploading = false;
          return 100;
        }
        return n + 10;
      });
    }, 500);
  }
</script>

<style>
  .upload-container {
    background-color: #f0f0f0;
    border: 2px dashed #ccc;
    padding: 2rem;
    text-align: center;
    border-radius: 8px;
    max-width: 400px;
    margin: auto;
  }

  .upload-button {
    background-color: #3498db;
    color: white;
    border: none;
    padding: 1rem 2rem;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;
    margin-top: 1rem;
  }

  .progress-bar {
    background-color: #ccc;
    height: 20px;
    border-radius: 5px;
    overflow: hidden;
    margin-top: 1rem;
  }

  .progress {
    height: 100%;
    background-color: #2ecc71;
    width: 0%;
    border-radius: 5px;
    transition: width 0.5s ease;
  }

  .upload-complete {
    color: #2ecc71;
    margin-top: 1rem;
  }
</style>

<div class="upload-container">
  <div>Select audio file to repair</div>
  <button class="upload-button" on:click={startUploadMock} disabled={uploading}>
    {uploading ? 'Uploading...' : 'Start Upload Mock'}
  </button>

  {#if uploading}
    <div class="progress-bar">
      <div class="progress" style="width: {$uploadProgress}%"></div>
    </div>
  {/if}

  {#if $uploadProgress === 100}
    <div class="upload-complete">Upload Complete!</div>
  {/if}
</div>

