Project Page: https://www.opencompute.org/projects/open-accelerator-infrastructure

# OCP-SVR-OAI-Open_Accelerator_Infrastructure

**UPDATE 19AUG24**
Source: https://ocp-all.groups.io/g/OCP-OAI/message/94

OAI Team,

             As witnessed, there has been a noticeable decrease in activity related to the Open Accelerator Infrastructure (OAI) workgroup within OCP.  With that said, we’d like to take a moment to reflect on what has been accomplished by the team, highlight a few challenges brought about by rapidly evolving AI architectures as well as provide an open invitation to all to get involved and define the next iteration of OAI.

             OAI work began in 2018 with the conceptualization of an idea for an Open Accelerator Module (OAM) that would mate with a Universal Base Board (UBB) that provided IO capability and expansion in addition to accelerator module power and connectivity.  The creation and contribution to OCP of these base specifications would in turn be the impetus for vendors to develop design specifications and products against.  2019 saw the release of OAM 1.0 while 2020 culminated with the release of both the OAM 1.1 base specification as well as the finalization of the UBB 1.0 base specification.  2022 brought about updated releases of both OAM and UBB 1.5 base specifications and ultimately, ahead of OCP Global Summit 2023, the workgroup contributed base specifications for OAM r2.0, UBB r2.0 as well as Exp r2.0, a major accomplishment and milestone.  The charter with which OAI was founded had been fulfilled, creating a series of base specifications that would inform vendors in the design and creation of their own design specifications and products.

             Post OAM/UBB/Exp r2.0, we are facing some challenges and uncertainty.
1.	The incredible pace of advancement is driving architectures well beyond the OAM/UBB scope in both power and scale.
2.	These architectures are trending to be highly optimized to specific architectures and likely customized on potentially a per customer basis.
3.	Architectures are being driven at the rack scale (vs UBB scale) and varying customer requirements are driving unique topologies and interconnects that hamper commonality and interoperability.
4.	These rack scale architectures are being highly influenced by the large-scale customers.  A successful specification is ultimately one that is created through the deep collaboration of both suppliers and consumers and participation by a critical mass of consumers would be critical to the successful adoption of any follow-on effort.  Any specification built upon a point of view that does not include the key adopters will no doubt find difficulty in adoption.
5.	As well, we currently see trends pushing higher power into the PCIe form factor that will fill the needs of sub 1kW GPUs that is currently addressed by OAI.
             Looking forward…..

The market has evolved significantly since the launch of the OAI effort. What began as a forward-looking concept to standardize infrastructure for diverse compute acceleration architectures has now entered a new phase. Today, we find ourselves at a crucial juncture where the industry is actively seeking breakthrough compute performance for AI and HPC applications.

So to assess where we are headed:

The initial OAI/UBB implementations have successfully demonstrated the viability and importance of universal acceleration solutions. To be sure, the market has rapidly progressed beyond these initial concepts, driven by the exponential growth in AI and HPC workloads. There's an increasing demand for solutions that can deliver unprecedented levels of performance, efficiency, and scalability.

We're observing a clear trend towards rack-scale architectures, which present both opportunities and challenges for the OAI community. These architectures allow for more efficient power distribution, cooling, and interconnects, but also require rethinking our approach to modularity and standardization. As a foundation we have launched the Open Systems for AI that tackle all of these larger issues. Acceleration is a key aspect.

While the original OAI concept aimed for broad standardization, we're now seeing a trend towards highly optimized, sometimes customer-specific solutions. This shift raises important questions about the role of open standards in a market that increasingly values customization for peak performance. We feel like this trend is antithetical to what our community wants.

The push for higher performance is driving up power requirements, often beyond the scope of current OAI specifications. If we were to use a magic wand and create an ideal acceleration solution, it would need to accommodate these higher power needs while maintaining flexibility and efficiency.

As we move to rack-scale and beyond, interconnect technologies become increasingly critical. There's an opportunity in defining or adopting standards for high-speed, low-latency interconnects that can scale from module to rack level.

The lines between hardware (HW) and software (SW) are blurring, with many advanced AI systems relying on tight integration between the two. There’s a huge opportunity to explore how to facilitate this HW/SW co-design approach while still maintaining openness and interoperability.

Success in this evolving landscape requires even closer collaboration between suppliers, consumers, and researchers. We should consider how to foster a more dynamic and inclusive ecosystem that can rapidly respond to emerging technologies and market needs.

Next Steps:
Given these developments, we believe it's time to reassess and potentially redefine the scope and goals of the OAI initiative. Synthesizing the history of OAI, the present market situation and where we think we need to go, we think there is an essential need to evolve the OAI concepts to be more performant, more heterogeneous, somehow more sustainable, and more supply chain friendly. Ultimately it would be great if everyone in the market could share/reuse design effort for high performance acceleration for AI/HPC workloads. This looks like a fork in the OAI roadmap from here. To make this happen, we propose the following steps:

1.	Community Survey: Conduct a comprehensive survey of OAI stakeholders to gather insights on current needs and future expectations. 
2.	Technical Workshop: Organize a workshop to explore emerging technologies and architectures that could inform the next generation of OAI specifications. 
3.	Use Case Analysis: Develop a set of forward-looking use cases that capture the diverse requirements of AI, HPC, and other emerging compute-intensive applications. 
4.	Roadmap Development: Based on the above inputs, create a new OAI roadmap that outlines how we can evolve our specifications and approach to meet future market needs. 
5.	Collaboration Framework: Establish a more agile collaboration framework that allows for rapid prototyping and iterative development of specifications.

We believe that by addressing these points and embracing the changing landscape, OAI can continue to play a crucial role in shaping the future of compute acceleration infrastructure. We invite all members of the OAI community to share their thoughts and actively participate in this next phase of our journey.
