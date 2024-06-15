<script>
  import { onMount } from "svelte";
  import gsap from "gsap";
  import{ ScrollTrigger} from "gsap/all";
  import Cursor from "../components/Helpers/Cursor.svelte";
  import {balls}from"../assets/scripts/spriteHero.js"
  gsap.registerPlugin(ScrollTrigger);
  

   


  //


  onMount(() => {
 balls();
  })

  

</script>

<style>
  .webgl {
  position: fixed;
  top: 0;
  left: 0;
  outline: none;
  overflow-x: hidden;
  z-index: 0;
}


</style>

<Cursor/>
<div class="-z-10 w-full h-full fixed bg-whiteP top-0"></div>
<canvas class="webgl"></canvas>
<div id="container"></div>


