<script>
 import ProjectLayout  from "./ProjectLayout.svelte";
 import { onMount } from "svelte";
 import HeaderProject from "./HeaderProject.svelte";
 import SectionProjectText from "./SectionProjectText.svelte";
 import MoreProjects from "./MoreProjects.svelte";
 import ImageBox from "./ImageBox.svelte";
 import ExternalLinks from "./ExternalLinks.svelte";


 let projectComponent ;
 let dataProject;
 let prevNextProjects;
 
 let item = 3;

 onMount(()=>{
	dataProject = projectComponent.getItemInfo(item);
	prevNextProjects = projectComponent.getPrevAndNext(item);
 })

</script>



<ProjectLayout  bind:this={projectComponent}>
	<!-- First section -->
	<HeaderProject dataProject={dataProject}></HeaderProject>
	<SectionProjectText
	headline="Concept">
	This installation explores the complex relationship between <b>non-machine 
	actors and machines </b> in the digital age. The installation challenges 
	participants to explore the potential interactions between the living
	and non-living agents as mediators between physical and digital realities.
	The immersion is presented as a conversation, but the result is an integrated
	experience of both actors navigating the real and the virtual space cooperatively.
	</SectionProjectText>
	<SectionProjectText
	headline="ReSEARCh / 
	INSPIRATION">

	For the exploration to blur the gap between machines and non-machines,
	the exploration started from a living thing like plants and through
	their physical properties different materials were explored to
	simulate the interaction of the plant with a computer. Two copies
	of the plant were created, one with <b>copper wire </b> and a second with
	<b>conductive clay</b>, to explore aspects such as the ability to conduct
	electricity and to provide a different level of abstraction of the plant.  
	
	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image1: ''} imageID={"abstract vs experiencial"}>
			<b>1:</b> Cupper wired plant &nbsp;
			<b>2:</b> Original plant &nbsp;
			<b>3:</b> Conductive clay &nbsp;
		</ImageBox>
	</div>

	</SectionProjectText>
	<SectionProjectText
	headline="PROTOTIPE
	SKETCH">

	For each input a simulation in TD has been assigned. Ranging from
	clusters of moving particles, lines and contours to very complex
	fluid dynamics. All these visual outputs were chosen based on
	being inspired by natural phenomena like air, moving flocks, shadows, etc.

    
	<ImageBox imageURL={dataProject != undefined ? dataProject.image4: ''} imageID={"abstract vs experiencial"}>
		<p> Capacitive sensor circuit switches and their output via serial comunication.
		</p>
	</ImageBox>

	</SectionProjectText>
	<SectionProjectText
	headline="Result">
	<div class="flex  flex-col">
		<video class="h-full block  overflow-hidden  py-2 wow fadeInUp" data-wow-duration="2s" loop autoplay muted>
			<source src={dataProject != undefined ? dataProject.video1: ''} type="video/mp4">
		</video>
		<div class="project-ref text-xs ">
			Video by Isabella Arturo Lee
		</div> 

		<ImageBox imageURL={dataProject != undefined ? dataProject.image2: ''}  imageID={"step1"}>
			Example of the gas and fire simulation trigger by having contanct with the plant
		</ImageBox>
		
	</div>


	</SectionProjectText>


	<ExternalLinks  dataProject={dataProject}></ExternalLinks>
	<div class=" lg:h-[450px] block overflow-hidden  px-4 lg:px-10  wow fadeInUp"  data-wow-duration="2s">
		<img  class="object-cover w-full h-full" src={dataProject != undefined ? dataProject.image3: ''} alt={dataProject != undefined ? dataProject.name : ''} />
	</div>

	<MoreProjects prevNextProjects={prevNextProjects != undefined ? prevNextProjects : ''}>
	</MoreProjects>

</ProjectLayout>
