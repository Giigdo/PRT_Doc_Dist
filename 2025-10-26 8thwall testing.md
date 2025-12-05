# 2025-10-26 - Scaniverse and 8th Wall AR Prototype Testing

## Timestamp
October 26, 2025, 11:00 AM - 4:45 PM (approximately 4.75 hours active work time, including 15-minute break)

## Information
- **Location**: Home - kitchen floor and workspace with Samsung Z Fold phone
- **Participants**: Solo work (Andrew McConnell)
- **Resources/Tools**: 
  - Samsung Z Fold phone (advanced model, no LiDAR)
  - Scaniverse app (mobile 3D scanning)
  - Blender 4.2.4 for Mac (open source 3D editing)
  - 8th Wall / Niantic Studio (web-based AR platform)
  - Canva (image target creation)
  - Perplexity (for instructional support)
  - Various surfaces: wooden base, white cotton fabric, white plate, kitchen floor
- **Purpose/Goals**: Test the feasibility of creating AR (augmented reality) educational content using readily available consumer technology and free/open-source software; evaluate accessibility for Indigenous communities to produce AR learning materials; document complete workflow from 3D scanning through AR deployment

## Description

This experimental session tested the complete pipeline for creating AR educational content using accessible consumer technology. The research question centered on whether Indigenous communities could create AR learning materials using readily available tools: smartphones, household items, and free/open-source software.

### Phase 1: 3D Object Scanning with Scaniverse (11:00 AM - 12:00 PM)

**Test Objects Selected:**
Three objects were chosen to represent different material properties and cultural contexts:
1. Iron owl figurine (~1.5" tall) - single color, moderate shininess, small scale
2. Red metal mint container (~2.5" tall) - elaborate design, shiny, color variation
3. Smudge shell (3" × 4.5" × 1" tall) - natural object, ceremonial (traditional but not sacred), mixed shiny/matte surfaces

**Experimental Variables Tested:**

*Background Surface:*
- Wooden base (original hypothesis: natural texture might interfere)
- White cotton fabric (hypothesis: uniform background would improve recognition)
- White reflective plate (hypothesis: rotation capability might help, reflections might hinder)

*Scan Duration:*
- Under 1 minute (following Scaniverse recommendations)
- 2+ minutes (testing if extended scanning improves quality)

*Camera Movement:*
- Standard phone orientation (camera at top)
- Inverted phone orientation (camera at bottom for better low angles)
- Rotating object vs. rotating camera

*Scan Format:*
- Mesh/photogrammetry (detailed texture capture)
- Geosplat (newer format with different processing)

**Key Discoveries from 10 Test Scans:**

*Background Surface Results:*
The white background hypothesis was thoroughly disproven. All seven attempts with white surfaces (fabric and plate) produced significantly worse results than wooden surfaces, with objects losing dimensional definition and bleeding extensively into backgrounds. Scan 1 (wooden surface, under 1 minute) produced the best owl results. Scan 8 (red container on wooden surface, under 1 minute) was described as "very successful" with clear object/background delineation.

*Camera Movement Critical Finding:*
Rotating the object while keeping the phone stationary completely failed (Scan 5). The phone must detect its own movement around the object for the photogrammetry algorithms to function. This represents a fundamental technical requirement that must be communicated in any instructional materials.

*Scan Duration Optimization:*
Extended scanning (2+ minutes) with varied speeds and image clarity waiting (Scan 7) produced worse results than shorter scans under 1 minute. Following Scaniverse's recommendation to avoid "overloading the system" proved correct.

*Format Comparison:*
Geosplat format (Scan 6) provided better object/ground separation but less detail than mesh/photogrammetry. Geosplat offers different export options (PLY, SPX files) that could be processed in other geosplatting tools, opening alternative workflows for future exploration.

*Object Geometry Challenge:*
Objects with curved bottoms (owl, shell) consistently showed object/platform bleeding regardless of other variables. The flat-bottomed mint container achieved clean separation. Testing with a completely spherical ball (Scan 10) produced "a mess" with no proper circular shape, confirming that rounded objects are "really difficult" to capture without LiDAR technology.

*Phone Camera Position:*
Attempting to improve angle coverage by inverting the phone (camera at bottom rather than top) produced worse results (Scan 4), though the software correctly oriented the final object right-side-up.

**Technical Resource Observations:**
Continuous scanning for 45 minutes consumed 20% of phone battery. The phone became warm but not critically hot. Environmental concerns were identified: hot weather (August) or outdoor scanning in direct sun could cause overheating and potential shutdown. This represents a practical limitation for certain field research scenarios.

### Phase 2: 3D Model Editing with Blender (12:30 PM - 1:17 PM, with 15-minute break)

The transition from Scaniverse to 8th Wall revealed that 8th Wall cannot edit objects directly within its platform. This necessitated finding external 3D editing software. Blender was selected because it met all research criteria:
- Open source
- Free access
- No account required
- Readily available for Mac

The workflow involved:
1. Downloading and installing Blender 4.2.4 (stable release, not beta/alpha)
2. Importing the .glb file from Scaniverse (shell scan selected for best detail)
3. Removing excess information (wooden platform, background elements)
4. Critical positioning: moving object to correct location and zeroing coordinates (x,y,z = 0,0,0)
5. Saving edited file

An interesting observation: in Blender, the object appeared as a gray mask without visible color or texture. However, upon import to 8th Wall, full shading and texture automatically appeared, indicating that texture data was preserved in the file even when not visually displayed in Blender.

The Blender phase required using Perplexity to access instructions, demonstrating an accessible learning pathway for users with "minimal knowledge." However, the researcher noted their own comfort level with software access and use, raising important questions about what truly constitutes "minimal knowledge" and what instructional depth is actually required for community members.

### Phase 3: Image Target Creation with Canva (1:17 PM - 2:00 PM)

Canva, another accessible free tool, was used to create the AR image target (trigger card). The process involved:
1. Finding a teacher-created playing card template
2. Swapping out one card image to create a custom AR trigger
3. Printing a test sheet with 4 different cards on a single page

The 4-card proximity test was designed to answer an important question: Would the AR system correctly identify only the designated target card, or would nearby images confuse the recognition system? This testability assessment would help understand practical limitations for classroom or community use where multiple AR materials might be present simultaneously.

### Phase 4: AR Experience Building with 8th Wall (2:00 PM - 4:45 PM, with break)

The final phase involved working through the Niantic Studio "Building with Image Targets for the Web" tutorial. Initial attempts encountered multiple false starts due to hierarchy issues and incorrect object placement within the 8th Wall interface. The solution came from running the tutorial from scratch while replacing tutorial images with project materials, allowing learning of proper workflow structure.

**8th Wall Import Process Discovery:**
The import method was not intuitive. Drag-and-drop did not function. The correct process required using the Files menu on the left side, clicking the plus button, then navigating to select the file.

**Testing Results:**
The final AR experience successfully functioned with both on-screen and printed image targets. A significant discovery emerged: the system worked equally well with black-and-white printed cards as with full-color screen displays. This indicates the recognition system identifies shapes and patterns rather than colors, which has practical implications for printing costs and accessibility.

The 4-card proximity test was successful - the system correctly identified only the target card despite multiple similar images in close proximity on a single sheet.

**File Formats Used:**
- Graphics: PNG
- 3D model: GLB  
- Print output: PDF from Canva
Assessment: "Nothing exotic, fairly straightforward files"

## Analysis & Reflection

### Strengths

**Comprehensive Systematic Testing:**
The experimental design tested multiple variables methodically: 10 complete scans across three objects, varying background surfaces, scan durations, camera orientations, and formats. This thorough approach generated robust findings rather than anecdotal observations.

**Clear Documentation of Technical Requirements:**
Each phase identified specific technical requirements and limitations that would need to be communicated in instructional materials: camera movement patterns, scan duration limits, object geometry constraints, software positioning requirements.

**Tool Selection Validation:**
All tools met research criteria for accessibility:
- Scaniverse: Free mobile app
- Blender: Open source, no account required
- Canva: Free access with teacher resources
- 8th Wall: Free tier available, web-based (no downloads)

**Discovery of Counterintuitive Results:**
The white background hypothesis being disproven represents valuable learning. Initial assumptions about optimal scanning conditions did not match actual results, generating important knowledge for future instruction development.

**Pedagogical Framework Emergence:**
The work naturally organized into a clear 3-4 class structure with defined learning objectives and approximately 1 hour per class session. This provides immediate practical application for educational contexts.

**Complete Workflow Validation:**
Successfully demonstrating the entire pipeline from scanning through AR deployment proves technical feasibility using accessible consumer technology.

### Challenges

**LiDAR Limitation Impact:**
The inability to successfully scan curved or spherical objects without LiDAR represents a significant limitation. While the Samsung Z Fold is an advanced phone, its lack of LiDAR prevented certain object types from being viable. This creates a technology accessibility issue: newer iPhones have LiDAR, but not all community members will have access to these devices.

**"Minimal Knowledge" Definition Uncertainty:**
The researcher's own comfort with software access and troubleshooting creates ambiguity about what instructional support is actually needed for true community accessibility. What appears "straightforward" to someone with technical facility may present substantial barriers to others.

**Environmental and Resource Constraints:**
Battery consumption (20% per 45 minutes) and heat generation limit extended field use, particularly in hot weather or outdoor contexts. This could restrict certain research or documentation scenarios.

**Learning Curve for 8th Wall:**
Multiple false starts with hierarchy and placement issues indicate a non-trivial learning curve for the AR platform. While ultimately successful, this suggests instruction needs careful scaffolding.

**Data Sovereignty Concerns:**
All software tools (Scaniverse, Blender, 8th Wall, Canva) and the phone operating system are owned by non-Indigenous entities. While this was acknowledged as "not immediately solvable," it remains a fundamental concern for Indigenous technology work that "rides underneath everything."

**Cropping Limitation:**
The discovery that cropping only works on mesh format (not photogrammetry) created workflow constraints. Object/background separation issues couldn't be resolved within Scaniverse, requiring external editing.

### Connections to Previous Work

**Indigenous AI and Technology Research:**
This work connects directly to ongoing research on Indigenous-controlled technology tools and data sovereignty concerns documented in previous PRT sessions (June-August 2025). The same underlying questions about platform ownership and community control apply to AR development tools.

**Educational Technology and Community Capacity Building:**
The pedagogical framework aligns with previous work on community-centered technology development and knowledge mobilization. The emphasis on accessible tools and training reflects established research directions in Indigenous design principles.

**360° Video and Immersive Media:**
This AR prototyping work complements extensive previous research on 360° video editing workflows and VR/AR technology testing documented in July 2025 PRT sessions. The findings about object scanning could potentially integrate with 360° environment capture for comprehensive immersive learning spaces.

**Neural Radiance Fields Workshop Learning:**
The May 2025 ISEA workshop on 3D Gaussian Splatting and NeRF technologies provides theoretical context for understanding different scanning and reconstruction approaches. The geosplat format option in Scaniverse represents a practical application of concepts explored in that workshop.

**Prototype Evaluation Methodology:**
This work directly implements the evaluation framework developed in the July 22, 2025 session on prototype evaluation methodology. The collect-create-host-present pipeline structure was applied systematically, and sovereignty concerns were actively tracked throughout.

### Emerging Questions

**LiDAR Accessibility and Alternative Solutions:**
How can communities without access to LiDAR-equipped devices successfully scan rounded objects? Are there software processing techniques that could compensate for missing hardware? Should instructional materials focus only on flat-bottomed objects when LiDAR is unavailable?

**True "Minimal Knowledge" Assessment:**
What does "minimal knowledge" actually mean for community members without technical backgrounds? How much instructional support is needed for each phase? What are the actual barriers to entry beyond tool access?

**Pedagogy Development and Testing:**
How would this 3-4 class structure actually function with different populations: high school students, community members, elders learning technology? What modifications would be needed for different contexts?

**Scaling and Implementation:**
Could this be implemented as a Communications Technology high school credit course? What partnerships with schools or community organizations would support broader adoption? How could project-based learning momentum build community capacity as suggested?

**Integration with Other Media:**
How could this AR object creation integrate with 360° video environments or other immersive media for comprehensive learning experiences? Could audio teachings be easily added? What extensions become possible once basic skills are established?

**Platform Alternatives and Sovereignty:**
What open-source alternatives exist to 8th Wall that might provide better community control? How could Indigenous communities build their own AR hosting infrastructure aligned with data sovereignty principles?

**Cross-Platform Consistency:**
Will this workflow function identically on iPhone with LiDAR? How do Android and iOS differences impact the process? What are the minimum viable phone specifications for each phase?

### Potential Improvements

**Systematic Testing with Indigenous Students:**
The researcher identified future research direction: testing this workflow with Indigenous students to determine actual knowledge requirements and necessary instruction depth. This represents critical next-phase work for validating accessibility claims.

**LiDAR Comparison Testing:**
Complete the planned testing using iPhone with LiDAR to establish what improvements become possible and whether curved object limitations can be overcome.

**Older Device Testing:**
Test with older phone models to establish minimum viable specifications for community accessibility. How far back in technology can the workflow still function?

**Alternative Software Exploration:**
Investigate other free/open-source AR platforms beyond 8th Wall to evaluate sovereignty implications and community control options.

**Instructional Material Development:**
Create comprehensive step-by-step guides appropriate for true beginners, informed by testing with diverse user populations.

**Environmental Scanning Integration:**
Building on NeRF/3DGS workshop learning, explore whether scanned objects can be integrated into scanned environments for complete immersive learning spaces.

## Conclusion

### Key Insights

**Technical Feasibility Established:**
The complete workflow from 3D scanning through AR deployment is achievable using accessible consumer technology and free/open-source software. The process is straightforward enough to be taught in 3-4 hour-long class sessions.

**LiDAR as Critical Limitation:**
Objects with curved geometries require LiDAR technology for successful scanning. Without LiDAR, focus must be on flat-bottomed objects or accept imperfect results with post-processing cleanup.

**Background Surface Counterintuitive:**
White backgrounds, despite seeming logical, produce consistently worse results than textured wooden surfaces. This represents important knowledge that contradicts intuitive assumptions.

**Camera Movement Essential:**
The phone must move around the object; rotating the object while keeping the phone stationary fails completely. This fundamental requirement must be clearly communicated in instructional materials.

**Optimal Scanning Duration:**
Shorter scans under 1 minute following Scaniverse recommendations produce better results than extended scanning attempts. More scanning does not equal better quality.

**AR Recognition Robust:**
The 8th Wall AR system successfully identifies target images in black-and-white print, recognizing shapes rather than colors. Multiple nearby images don't confuse the system when properly configured.

**Data Sovereignty Fundamental Concern:**
While technical feasibility is proven, all tools remain under non-Indigenous corporate control. This unresolved tension "rides underneath everything" and represents a fundamental limitation of current accessible technology.

**Community Capacity Building Potential:**
Project-based learning momentum could support community capacity development: completing one project enables people to do more, creating positive cycles of skill development and confidence.

### Decisions Made

**Object Selection for Demonstration:**
Smudge shell selected as primary demonstration object for comprehensive exam prototypes due to good scan quality, cultural significance (traditional/ceremonial but not sacred), and successful AR implementation.

**Pedagogical Framework Adoption:**
Implement 3-4 class structure: (1) Scaniverse scanning, (2) Blender editing, (3/4a) Canva image target creation, (4/4b) 8th Wall AR building. Each session approximately 1 hour.

**Tool Stack Validation:**
Continue using Scaniverse, Blender, Canva, and 8th Wall as the recommended accessible tool stack for community AR development, acknowledging sovereignty limitations while providing immediate viable pathways.

**Documentation and Materials:**
All materials saved to OneDrive under Prototypes folder for comprehensive exam demonstrations. QR code to be printed and included with image target card for complete demonstration package.

**Future Collaboration Planning:**
Identified potential implementation with Shaq through Abundant Intelligences work, school classroom pilots, and community workshop opportunities.

### Next Steps

**Immediate:**
- Print QR code to accompany image target card
- Organize complete demonstration materials for comprehensive exam
- Document specific technical specifications and settings used

**Short-term Testing:**
- Test workflow with iPhone (LiDAR capability) to establish performance differences
- Test with older phone models to determine minimum viable specifications
- Evaluate cropping capabilities across different software tools
- Explore alternative open-source AR platforms

**Medium-term Research:**
- Design and conduct testing with Indigenous students to establish true "minimal knowledge" requirements and necessary instructional support
- Develop comprehensive instructional materials informed by user testing
- Create evaluation rubrics for different user populations and contexts
- Investigate integration possibilities with 360° video and other immersive media

**Long-term Development:**
- Explore Communications Technology high school credit course development
- Establish school and community partnerships for pilot implementations
- Investigate Indigenous-owned/controlled AR platform alternatives
- Research community-hosted infrastructure options for data sovereignty
- Develop extensions: audio teaching integration, original Blender modeling, expanded object libraries

### Impact on Research Trajectory

**Comprehensive Exam Prototype Validation:**
This work successfully demonstrates technical feasibility for one of the comprehensive exam prototypes, providing concrete evidence of community-accessible AR development pathways using readily available technology.

**Indigenous Design Principles Application:**
The systematic testing of tools against accessibility criteria (open-source, free, no accounts, readily available) represents practical application of community-centered design principles that inform broader PhD research directions.

**Knowledge Mobilization Framework:**
The emergent 3-4 class pedagogical structure provides a concrete model for knowledge mobilization: not just creating technology but creating transferable skills and community capacity for ongoing independent development.

**Data Sovereignty Ongoing Concern:**
This work reinforces the fundamental tension between accessibility (using existing free tools) and sovereignty (community control over technology and data). This tension continues to "ride underneath" all Indigenous technology research and requires ongoing attention in dissertation work.

**Methodology Refinement:**
The systematic experimental approach with multiple controlled variables demonstrates effective research methodology for evaluating technology accessibility. This approach can be applied to future prototype testing and community technology assessment.

**Integration with Broader Research:**
This AR object creation work connects to multiple ongoing research threads: 360° video workflows, immersive learning environments, Indigenous AI development, community capacity building, and educational technology design. The AR component adds another dimension to the comprehensive ecosystem of Indigenous educational technology being developed.

**Future Research Directions:**
Clear pathways emerged for future investigation: Indigenous student testing for true accessibility assessment, LiDAR comparison studies, platform sovereignty alternatives, and integration with other immersive media types. The work generates more questions than it answers, indicating productive research directions.

**Practical Community Applications:**
Beyond theoretical contributions, this work creates immediate practical opportunities: classroom implementations, community workshops, cultural documentation projects, and educational resource development. The prototype serves dual purposes as both research artifact and deployable community tool.

## Associated Materials

**3D Scans Created:**
- 10 total scans across 3 objects (iron owl, red mint container, smudge shell)
- Formats: Mesh/photogrammetry and geosplat
- Best results: Scan 1 (owl, wooden surface, <1 min), Scan 8 (mint container, wooden surface, <1 min), Scan 9 (shell, wooden surface, with detail passes)
- File locations: Scaniverse app library and exported to OneDrive/Prototypes

**Edited 3D Models:**
- Smudge shell GLB file edited in Blender
- Background removed, coordinates zeroed, positioned for AR import
- File location: OneDrive/Prototypes

**Image Targets:**
- Canva playing card template with custom image
- 4-card test sheet (PDF)
- Printed versions: full color and black & white successful
- File location: OneDrive/Prototypes

**AR Experience:**
- 8th Wall/Niantic Studio project files
- Working AR implementation with shell model and card trigger
- QR code for deployment (to be printed)
- Access link: [8th Wall project URL]

**Documentation:**
- Complete session notes with timestamps and technical observations
- Perplexity search results for Blender instructions
- Tutorial: "Building with Image Targets for the Web" (Niantic Studio)

**Hardware Specifications:**
- Samsung Z Fold (advanced model, no LiDAR)
- Battery consumption data: 20% per 45 minutes continuous scanning
- Heat generation observations

**Software Versions:**
- Scaniverse: [current version as of August 2025]
- Blender 4.2.4 for Mac (stable release)
- 8th Wall/Niantic Studio (web-based platform)
- Canva (web-based platform)

**Test Results Summary:**
- 10 scans documented with quality assessments
- Background surface comparison data (wooden vs. white)
- Scan duration optimization findings
- Format comparison (mesh vs. geosplat)
- Object geometry limitations (flat vs. curved bottoms)

**Future Testing Materials:**
- List of alternative AR platforms to evaluate
- iPhone testing protocol for LiDAR comparison
- Older device specifications for backward compatibility testing
- Community testing protocols for Indigenous student evaluation
