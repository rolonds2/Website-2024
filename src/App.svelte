<script>
  import { Router, Route } from "svelte-routing";
  import { onMount } from "svelte";
  import gsap from "gsap";


  // No Layout Pages
  import Index from "./views/Index.svelte";
  import About from "./views/About.svelte";
  import Contact from "./views/Contact.svelte";
  import FairGame from "./views/Projects/FairGame.svelte";
  import TheWayOfTheRabbit from "./views/Projects/TheWayOfTheRabbit.svelte";
  import LikeAGlitch from "./views/Projects/LikeAGlitch.svelte";
  import LivingTheBogotazo from "./views/Projects/LivingTheBogotazo.svelte";
  import Biamp from "./views/Projects/Biamp.svelte";
  import AutismSocietyAmerica from "./views/Projects/AutismSocietyAmerica.svelte";
  import Nexgen from "./views/Projects/Nexgen.svelte";
  import Guardians from "./views/Projects/Guardians.svelte";
  import BicentenaryHeroes from "./views/Projects/BicentenaryHeroes.svelte";
  import Nod from "./views/Projects/Nod.svelte";


 

  export let url = "";

  onMount(() => {
    new WOW().init();
    gsap.config({ nullTargetWarn: false });
 
  })

  
</script>



<Router url="{url}" >
  <!-- no layout pages -->
  <Route path="/" component="{Index}"  />
  <Route path="/home" component="{Index}" />
  <Route path="/contact" component="{Contact}" />
  <Route path="/about" component="{About}" />
  


  <!-- pages with layout -->
  <Route path="/fair-game" component="{FairGame}" />
  <Route path="/the-way-of-the-rabbit" component="{TheWayOfTheRabbit}" />
  <Route path="/like-glitch-in-a-frame" component="{LikeAGlitch}" />
  <Route path="/living-the-bogotazo" component="{LivingTheBogotazo}" />
  <Route path="/biamp" component="{Biamp}" />
  <Route path="/autismsocietyamerica" component="{AutismSocietyAmerica}" />
  <Route path="/nexgen" component="{Nexgen}" />
  <Route path="/guardians-innitiative" component="{Guardians}" />
  <Route path="/bicentenary-heroes" component="{BicentenaryHeroes}" />
  <Route path="/nod" component="{Nod}" />
  
 



</Router>
