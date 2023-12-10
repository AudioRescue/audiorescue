<script lang="ts">
  import Intro from "../components/intro.svelte";
  import Hero from "../components/hero.svelte";
  import Features from "../components/features.svelte";
  import Navbar from "../components/navbar.svelte";
  import Maincontent from "../components/maincontent.svelte";
</script>

<!-- <svg -->
<!--   xmlns="http://www.w3.org/2000/svg" -->
<!--   version="1.1" -->
<!--   xmlns:xlink="http://www.w3.org/1999/xlink" -->
<!--   width="100%" -->
<!--   height="100%" -->
<!--   preserveAspectRatio="xMidYMid slice" -->
<!--   viewBox="0 0 1440 560" -->
<!-- > -->
<!--   <g mask="url(&quot;#SvgjsMask1113&quot;)" fill="none"> -->
<!--     <path -->
<!--       d="M -704.8581381269108,301 C -608.86,290.2 -416.86,246.2 -224.85813812691083,247 C -32.86,247.8 63.14,302.8 255.14186187308917,305 C 447.14,307.2 543.14,217.6 735.1418618730892,258 C 927.14,298.4 1074.17,537.4 1215.141861873089,507 C 1356.11,476.6 1395.03,186.2 1440,106" -->
<!--       stroke="rgba(226, 65, 247, 0.8)" -->
<!--       stroke-width="2" -->
<!--       filter="url(#glow)" -->
<!--     /> -->
<!--     <path -->
<!--       d="M -718.862447936566,357 C -622.86,316 -430.86,134.2 -238.86244793656607,152 C -46.86,169.8 49.14,439.8 241.13755206343393,446 C 433.14,452.2 529.14,203.2 721.137552063434,183 C 913.14,162.8 1057.37,351.4 1201.137552063434,345 C 1344.91,338.6 1392.23,189.8 1440,151" -->
<!--       stroke="rgba(115, 249, 251, 0.8)" -->
<!--       stroke-width="2" -->
<!--       filter="url(#glow)" -->
<!--     /> -->
<!--     <path -->
<!--       d="M -635.8239753076191,344 C -539.82,288.6 -347.82,63.2 -155.82397530761907,67 C 36.18,70.8 132.18,336.2 324.1760246923809,363 C 516.18,389.8 612.18,216.8 804.1760246923809,201 C 996.18,185.2 1157.01,308 1284.176024692381,284 C 1411.34,260 1408.84,121.6 1440,81" -->
<!--       stroke="rgba(115, 122, 251, 0.5)" -->
<!--       stroke-width="2" -->
<!--       filter="url(#glow)" -->
<!--     /> -->
<!--     <path -->
<!--       d="M -732.9670131127448,348 C -636.97,296.6 -444.97,70.6 -252.96701311274478,91 C -60.97,111.4 35.03,447.8 227.03298688725522,450 C 419.03,452.2 515.03,93.6 707.0329868872552,102 C 899.03,110.4 1040.44,496.8 1187.0329868872552,492 C 1333.63,487.2 1389.41,160.8 1440,78" -->
<!--       stroke="rgba(115, 122, 251, 0.5)" -->
<!--       stroke-width="2" -->
<!--       filter="url(#glow)" -->
<!--     /> -->
<!--   </g> -->
<!--   <defs> -->
<!--     <mask id="SvgjsMask1113"> -->
<!--       <rect width="1440" height="560" fill="#ffffff" /> -->
<!--     </mask> -->
<!--     <filter id="glow"> -->
<!--       <feGaussianBlur stdDeviation="3.5" result="coloredBlur" /> -->
<!--       <feMerge> -->
<!--         <feMergeNode in="coloredBlur" /> -->
<!--         <feMergeNode in="SourceGraphic" /> -->
<!--       </feMerge> -->
<!--     </filter> -->
<!--   </defs> -->
<!-- </svg> -->
<Navbar />
<Hero />
<Intro />
<Features />
<Maincontent />

<!-- <PricingSection /> -->
