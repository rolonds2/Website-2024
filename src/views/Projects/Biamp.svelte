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
 
 let item = 5;

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
	
	<p><b>Biamp City</b> is a web platform designed to cover the entire Biamp 
	   product range in context. It offers detailed information about 
	   specific <b>product families</b> and documents how different categories 
	   of products <b>work together</b> to provide solutions for various needs.
	</p>

	</SectionProjectText>
	<SectionProjectText
	headline="ReSEARCh / 
	INSPIRATION">

	<p>Unlike traditional catalogs, the exploration concept of Biamp 
	took reference from <b>8 primary venues</b> or industries where it provides 
	services. Mapping these points demonstrates the extensive portfolio of 
	solutions.However, delving deeper into each venue unveils specific use 
	cases, showcasing <b>Biamp's comprehensive </b>approach to crafting tailored 
	solutions in an integral way.</p>

	<br>

	<p>
	The style maintains a minimalist approach, utilizing wireframes 
	to depict the venues. This prioritizes the <b>selectable/interactable elements</b>
	and colored icons, which represent the various products that are 
	the protagonism of the space.
	</p>

	
	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image2: ''} imageID={"abstract vs experiencial"}>
			Example of buildings and interiors stripped of detail to add the solutions information layer. Photo by Watson Creative &nbsp;
		</ImageBox>
	</div>



	</SectionProjectText>
	<SectionProjectText
	headline="PROTOTIPE
	SKETCH">


	<p>A family of <b>colour-coded</b> icons has been created for the devices,
	making it easy to group similar devices and categorise specific 
	functions. For example, everything in dark blue was the speaker group,
	and dark yellow was the microphone group.</p>

	<br>
	<p>The implementation of the <b>breadcrumbs</b> was essential to guide the
	navigation, as it indicated not only the room, but also the previous
	 steps to get there, and how detailed the level of navigation was.</p>




	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image1: ''} imageID={"abstract vs experiencial"}>
			UI main components that guide the navigation. &nbsp;
		</ImageBox>
	</div>


	</SectionProjectText>
	<SectionProjectText
	headline="Result">

	<ImageBox imageURL={dataProject != undefined ? dataProject.image3: ''}  imageID={"step1"}>
		<b>(Step):</b>
		1. Biamp City with the 8  main venues with a red overlay to trigger the interaction. &nbsp;
	
	</ImageBox>
	<ImageBox imageURL={dataProject != undefined ? dataProject.image4: ''}  imageID={"step2"}>
		<b>(Step):</b>
		2. Each contains a set of sub-scenarios including shortcuts to the most requested solutions. &nbsp;
	</ImageBox>

	<ImageBox imageURL={dataProject != undefined ? dataProject.image6: ''}  imageID={"step3"}>
		<b>(Step):</b>
		3. Indoors or Outdoors the spaces display array of the devices build the solutions coupled with its technical manual. &nbsp;
	</ImageBox>


	</SectionProjectText>
	<ExternalLinks  dataProject={dataProject}></ExternalLinks>
	<div class=" lg:h-[450px] block  overflow-hidden  px-4 lg:px-10  wow fadeInUp"  data-wow-duration="2s">
		<img  class="object-cover w-full" src={dataProject != undefined ? dataProject.image5: ''} alt={dataProject != undefined ? dataProject.name : ''} />
	</div>

	<MoreProjects prevNextProjects={prevNextProjects != undefined ? prevNextProjects : ''}>
	</MoreProjects>

</ProjectLayout>
