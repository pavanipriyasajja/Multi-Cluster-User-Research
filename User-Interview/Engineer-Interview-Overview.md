<h2>Beyond Survey Findings: Why We Conducted In-Depth User Interviews</h2>

The initial multi-cluster research gathered insights from 170 engineers through a survey. These findings helped identify common operational challenges, user needs, and patterns across multi-cluster environments. Based on the survey results, we developed a Hybrid Engineer persona and user journey map to better understand engineers' responsibilities, goals, pain points, and workflows.

However, while these research methods provide a strong foundation, they do not fully capture the complexity of real-world multi-cluster operations.

<h2>Why are survey data, the Hybrid Engineer persona, and journey mapping not sufficient?</h2>

- <b>Limited depth of understanding</b>: Surveys identify what challenges engineers experience but often do not explain why these challenges occur or how engineers address them.
- <b>Lack of real-world workflow details:</b> Survey responses provide a broad understanding of deployment, observability, and maintenance challenges but do not fully capture the step-by-step processes engineers follow.
- <b>Personas represent generalized behaviors:</b> The Hybrid Engineer persona summarizes common characteristics, responsibilities, and pain points but cannot represent every engineer's unique infrastructure, tools, and operational environment.
- <b>Journey maps are based on reported experiences:</b> Journey mapping helps visualize user activities, challenges, and opportunities, but survey-based maps may miss unexpected problems, workarounds, and decisions made during actual operations.
- <b>Limited understanding of root causes:</b> Surveys highlight recurring problems such as fragmented observability, configuration drift, and operational complexity but provide limited evidence about their underlying causes.
- <b>Insufficient context for solution development:</b> Survey findings help identify opportunities for improvement, but additional research is needed to validate user needs and develop practical solutions.


<h2>Why do we need to conduct 1:1 user interviews with engineers?</h2>

To address these research gaps, we conducted 1:1 interviews with engineers to gain a deeper understanding of their real-world multi-cluster experiences, workflows, and operational challenges.

- <b>Understand real-world workflows:</b> Explore how engineers deploy applications, monitor cluster health, troubleshoot failures, and perform maintenance across multiple Kubernetes clusters.
- <b>Investigate challenges in depth:</b> Understand why specific problems occur, their impact on daily operations, and how engineers currently resolve them.
- <b>Identify hidden challenges and workarounds:</b> Discover manual processes, unexpected failures, and operational difficulties that were not captured in survey responses.
- <b>Understand decision-making processes:</b> Learn how engineers make decisions during deployments, incidents, upgrades, and recovery operations.
- <b>Explore different operational environments:</b> Understand how challenges vary depending on cluster scale, infrastructure, organizational structure, and tooling.
- <b>Validate and expand survey findings:</b> Confirm whether previously identified challenges reflect real-world experiences while discovering new problems and user needs.
- <b>Identify actionable improvement opportunities:</b> Gather detailed evidence to inform better tooling, automation, usability, and developer experience improvements.


<h2>How do these research methods complement each other?</h2>

Research method	& Primary contribution
<b>Survey (170 engineers):</b>	Identifies common challenges, needs, and operational patterns across multi-cluster environments.

<b>Hybrid Engineer Persona:</b>	Represents shared user characteristics, responsibilities, goals, and frustrations.

<b>Journey Mapping:</b>	Visualizes user workflows, pain points, and improvement opportunities based on survey findings.

<b>1:1 User Interviews:</b>	Explores the underlying causes, real-world workflows, decision-making, and challenges not captured by surveys.


<h2>Key Research Objectives</h2>

<b>Understand Real-World Multi-Cluster Workflows</b>: We aimed to understand how engineers managed deployments, monitored cluster health, troubleshot incidents, and performed maintenance across multiple Kubernetes clusters.

<b>Explore Operational Challenges in Depth</b>: We investigated the underlying causes of deployment failures, fragmented observability, maintenance complexity, and other operational challenges identified in the survey.

<b> Identify Hidden Challenges and Workarounds</b>: We explored manual processes, unexpected failures, tool limitations, and workarounds that were not fully captured through survey responses.

<b> Understand Engineering Decision-Making</b>: We examined how engineers made decisions during deployments, incident investigations, upgrades, and recovery operations, including how they assessed risks and validated system health.

<b>Validate and Expand Previous Research Findings</b> : We aimed to understand how the challenges identified through the survey, Hybrid Engineer persona, and journey mapping aligned with engineers' real-world experiences and to uncover additional needs.

<b> Identify Opportunities to Improve Developer Experience : </b> We sought to identify actionable improvements to multi-cluster tooling, automation, operational visibility, and workflow efficiency.

<h2>Research Methodology</h2>

<b>Research Approach</b>

We used a qualitative research approach, conducting semi-structured 1:1 interviews with engineers who had practical experience working with Kubernetes multi-cluster environments.

Unlike the initial survey, which provided a broad understanding of common operational challenges, these interviews allowed us to explore individual experiences, technical environments, operational decisions, and challenges in greater depth.

We used open-ended questions and follow-up discussions to encourage participants to describe their real-world experiences, workflows, and specific examples of operational difficulties.

<b>Participant Recruitment</b>
We recruited participants through outreach to the Kubernetes and cloud-native communities, including professional networks and community communication channels.
We invited engineers with relevant multi-cluster experience to share their operational workflows, challenges, and perspectives through individual research interviews. We sent the email invite to all of the participants who participated in the Surveys and interested in participating in follow-up user interviews. 

<b>Interview Format</b>
We conducted individual, semi-structured interviews using open-ended questions.
Each interview focused on understanding the participant's engineering responsibilities, Kubernetes environment, tools, operational workflows, and real-world challenges.
The semi-structured format allowed us to maintain consistency across interviews while providing flexibility to investigate unexpected challenges and follow up on relevant experiences.

Research conducted through <b>Google Meet, Communication platform with participants : Email</b>

<b>Research data analysis:</b> Clean up the raw data + labeling and coding the raw data + pattern identification + Thematic analysis (To learn more about the process of analysis please read our documentation form the Github repo: https://github.com/pavanipriyasajja/Multi-Cluster-User-Research/blob/main/Surveys/Analysis-Process-Methods.md 


<h2>Research Focus Areas</h2>

The interviews explored three primary operational workflows.

<b>1. Deployment Workflows</b>
We investigated how engineers deployed applications and infrastructure changes across multiple clusters, including deployment strategies, automation, rollout validation, failures, and recovery processes.

<b>2. Observability Workflows</b>
We explored how engineers monitored cluster and application health, investigated incidents, correlated information across tools, identified root causes, and validated recovery.

<b>3. Maintenance Workflows</b>
We examined how engineers performed cluster upgrades, configuration changes, security updates, and lifecycle management while minimizing operational risks and service disruptions.








