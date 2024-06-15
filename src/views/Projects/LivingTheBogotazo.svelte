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
 
 let item = 4;

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
	
	<p>To illustrate this event called <b>"El Bogotazo,"</b> we
		designed an experience for traveling back to
		that time. The time machine is an antique
		telephone which rings when a user walks in
		front of it. If the user raises the speaker, a
		recovered radio broadcasting audio is heard
		telling in real time how this event happened.
	</p>

	</SectionProjectText>
	<SectionProjectText
	headline="ReSEARCh / 
	INSPIRATION">

	<p>As part of the commemoration of the <b>480th</b> anniversary of  the capital fundation at the <b>Bogotá 
	International Book Fair</b>, an interactive timeline was placed to display the history
	of the city.</p>

	<br>

	<p>One of the most significant moments in the chronology unfolded in the <b>40s </b>
	when an opposition leader was assassinated, sparking a rebellion that ravaged 
	a notable portion of the town. As a way to connect people with the event, a 
	series of old telephones were installed to <b>facilitate communication</b> with the 
	old inhabitants of that time and reconstruct the events.</p>


	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image5: ''} imageID={"abstract vs experiencial"}>
			Photo by Pony Semana Magazine. &nbsp;
		</ImageBox>
	</div>
	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image4: ''} imageID={"abstract vs experiencial"}>
			Bogotá International Book Fair installation dedicated to the birthday of the capital. &nbsp;
		</ImageBox>
	</div>



	</SectionProjectText>
	<SectionProjectText
	headline="PROTOTIPE
	SKETCH">


	<p>When people walk within 30-50 cm of the phone, the reading from the ultrasonic 
	sensor activates the phone's ringer. Also, to preserve the audio style of the period,
	the phone's loudspeaker was used to play an audio from the local radio narrating
	the events.</p>
	<br>
	<p>When receiver is putted down, the audios are stopped and restarted.
		The following audio is selected randomly.
	</p>



	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image6: ''} imageID={"abstract vs experiencial"}>
			Visualization of the activation area relative to a person walking on front of the timeline. &nbsp;
		</ImageBox>
	</div>


	</SectionProjectText>
	<SectionProjectText
	headline="Result">

	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image3: ''} imageID={"abstract vs experiencial"}>
			Two phones placed at different heights allowed kids and adults to interact with the installation. Photo by Critertec &nbsp;
		</ImageBox>
	</div>

	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image2: ''} imageID={"abstract vs experiencial"}>
			Mayor of the city trying the installation. Photo by Critertec &nbsp;
		</ImageBox>
	</div>
	
	

	</SectionProjectText>

	<ExternalLinks  dataProject={dataProject}></ExternalLinks>
	<div class=" lg:h-[450px] block overflow-hidden  px-4 lg:px-10  wow fadeInUp"  data-wow-duration="2s">
		<img  class="object-cover w-full" src={dataProject != undefined ? dataProject.image1: ''} alt={dataProject != undefined ? dataProject.name : ''} />
	</div>

	<MoreProjects prevNextProjects={prevNextProjects != undefined ? prevNextProjects : ''}>
	</MoreProjects>

</ProjectLayout>
