<script>
 import ProjectLayout  from "./ProjectLayout.svelte";
 import { onMount } from "svelte";
 import HeaderProject from "./HeaderProject.svelte";
 import SectionProjectText from "./SectionProjectText.svelte";
 import MoreProjects from "./MoreProjects.svelte";
 import ImageBox from "./ImageBox.svelte"
 import ExternalLinks from "./ExternalLinks.svelte";

 let projectComponent ;
 let dataProject;
 let prevNextProjects;
 
 let item = 6;

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
	
	<p>This website is the result of a comprehensive rebranding effort
		for the <b>Autism Society of America</b>. It aims to create a unified 
		online community for all stakeholders, providing support, information,
		and resources tailored to their needs- all within the umbrella of <b>accessibility and inclusion.</b>.
	</p>

	</SectionProjectText>
	<SectionProjectText
	headline="ReSEARCh / 
	INSPIRATION">

	<p>As a starting point, the group of creatives involved determined
	the strategic direction of the organisation through a series of
	interviews with different <b>community stakeholders</b> and an analysis of
	other organisations in the same ecosystem. This step provided the
	valuable assets to guide the design of the website, on the one hand
	the <b>brand identity</b>, the <b>current user flow</b> and, on the other hand,
	the profile of the different <b>user personas</b>.

	</p>
	<br>
	<p>In addition, a brand image was developed to <b>guide the design system</b>
	with a palette of colours, typography and patterns that embody 
	connection and diversity.
	</p>
	
	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image2: ''} imageID={"abstract vs experiencial"}>
			The old website contained huge amounts of valuable information sometimes inaccesible  by the current design or occluded by outdated content. &nbsp;
		</ImageBox>
	</div>



	</SectionProjectText>
	<SectionProjectText
	headline="PROTOTIPE
	SKETCH">

	<p>
	For the prototype, the old content of the website has been 
	expanded into a diagram. This allows us to see which information
	is of interest to one, two or all of the personas. Additionally,
	each parent and child pages were tagged with colours associated 
	with <b>4</b> actionables for the three personas: <b>Learn, Make Impact, 
	Find Support, Resources,and Grow</b>. This helped to create more 
	consistent pathways through the website. It also helped to connect 
	the actionables and avoid dead ends in the navigation.

	</p>


	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image3: ''} imageID={"abstract vs experiencial"}>
			<b>(Left to right)</b>:
			Old Sitemap with overlaping between actionables vs new one with a more organized entry points depending the actionable. &nbsp;
		</ImageBox>
	</div>

	
	<div class="flex flex-col lg:flex-row">
		<ImageBox imageURL={dataProject != undefined ? dataProject.image4: ''} imageID={"abstract vs experiencial"}>
			New updates include tags for finding resources and blogs, content filtering and more concise information blocks. &nbsp;
		</ImageBox>
	</div>


	</SectionProjectText>
	<SectionProjectText
	headline="Result">
	<p>
		The design of the new homepage emphasizes several key principles. Firstly, 
		it focuses on being informative without overwhelming new members. Secondly, 
		it aims to build trust through transparency and clear information about the 
		organization. And lastly, it prioritizes inclusivity by empowering people 
		on the spectrum. This empowerment is achieved through appropriate navigation,
		allowing them to access testimonials, participate in events, or gain better
		insights into everyday issues.
	</p>

	<ImageBox imageURL={dataProject != undefined ? dataProject.image5: ''}  imageID={"step1"}>
		The new homepage serves as a starting guide, providing concise answers to key questions
		for newcomers. Additionally, it incorporates welcoming calls to action (CTAs) that underscore the commitment to open support. &nbsp;
	
	</ImageBox>
	<ImageBox imageURL={dataProject != undefined ? dataProject.image6: ''}  imageID={"step2"}>
		Tags with colors, filters to narrow information and descriptive menus boost indepence and make the navigation more intuitive.  &nbsp;
	</ImageBox>



	</SectionProjectText>
	<ExternalLinks  dataProject={dataProject}></ExternalLinks>
	<div class=" lg:h-[450px] block  overflow-hidden  px-4 lg:px-10  wow fadeInUp"  data-wow-duration="2s">
		<img  class="object-cover w-full" src={dataProject != undefined ? dataProject.image7: ''} alt={dataProject != undefined ? dataProject.name : ''} />
	</div>

	<MoreProjects prevNextProjects={prevNextProjects != undefined ? prevNextProjects : ''}>
	</MoreProjects>

</ProjectLayout>
