<script lang="ts">
  import Intro from '../components/Intro.svelte';
  import Content from '../components/content.svelte';
import Hero from '../components/hero.svelte';
  import Maincontent from '../components/maincontent.svelte';
  import Mock from '../components/mock.svelte';
  import Navbar from '../components/navbar.svelte';
  import PricingSection from '../components/pricing-section.svelte';
  import Services from '../components/services.svelte';
</script>
<Navbar />
<Hero />
<Intro />
<Services />
<Maincontent />
<Content 
	text1="We are a team of audio engineers with over a decade of experience in audio repair. We offer a range of services to bring your equipment back to life."
 	title="Welcome to AudioFix"
  	image="/hero.png"
   	checkmarks={["Audio File Repair", "Sound Quality Enhancement", "Noise Reduction", "Audio Restoration"]}
	/>
<Mock />
<PricingSection />
