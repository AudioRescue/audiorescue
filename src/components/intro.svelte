<script lang="ts">
  import InViewWrapper from "./in-view-wrapper.svelte";


</script>


<div class="intro-section" >
  <InViewWrapper transitionDuration={2000}>
  <h1 class="intro-title">Transform Your Content with Crystal-Clear Audio</h1>
  </InViewWrapper>
  <p class=" p">
    Turn your recordings into professional, broadcast-quality productions. Experience fast turnaround, personalized service,
    and the clarity your content deserves.
  </p>
</div>

<style>
  .intro-section {
    color: #fff;
    padding: 3rem 2rem;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 5rem auto 0 auto;
    position: relative;
    width: clamp(300px, 85vw, 800px);
    background: rgb(var(--color-background-secondary));
    border-radius: 10px;
    outline: 3px solid rgba(var(--color-accent-secondary), 0.2);
    top: -10rem;
  }
  .intro-section::before {
    content: "";
    position: absolute;
    right: 0;
    top:0%;
    bottom: 50%;
    width: 60rem;
    height: 30rem;
    background: radial-gradient(
      40% 80% at 90% 30%,
      var(--color-primary) 0%,
      rgba(255, 255, 255, 0) 90%
    );
    z-index: -1;
    animation: blob 10s linear infinite ;
    filter: blur(10px);
  }
  @media (prefers-reduced-motion: reduce) {
    .intro-section::before {
      animation: none;
    }
  }

  .intro-title {
    font-size: 2.8rem;
    margin-bottom: 1.5rem;
    max-width: 1000px;
  }

  @media (max-width: 768px) {
    .intro-title {
      font-size: 2.2rem;
    }
  }
  @keyframes float {
	0% {
		transform: translatey(0px);
	}
	50% {
		transform: translatey(-20px);
	}
	100% {
		transform: translatey(0px);
	}
}
  @keyframes blob {
  0%,100% {
    background-size: 100% 100%;
  }
  50% {
    background-size: 115% 115%;
  }
}
</style>
