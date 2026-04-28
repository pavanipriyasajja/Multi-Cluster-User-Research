## User Research Survey results report:


This report shares what we learned from our user research survey. Our <a href="https://multicluster.sigs.k8s.io/ ">SIG-multi cluster</a> is not only focusing on reducing technical complexity but also focusing on the human side - That’s where our UX research began.

Our <b>goal is simply make complex multi cluster systems easy to use and turn difficult operations into smooth and engineer friendly</b>. We designed surveys for <b>engineers who work with multi clusters</b>. We focused on <b>problem areas on Tooling, Environment, Troubleshooting, Observability, and Collaboration, workflows, architecture, multicluster management and deployment and debugging the challenges when they occur</b>. We included both <b>quantitative and qualitative</b> questions to understand how engineers work, what they use, and why they make certain choices.
We sent this survey to <b>SIG community channels</b> and received responses from <b>170 engineers</b>. To analyze the research data, we used a <b>text analyzer for written responses</b> and <b>Python for numerical data</b>. This helped us identify <b>patterns between demographics, tools, and challenges, multicluster operations</b>.
(Here is the more information about the method selection and the analysis process= 
<a href="https://Surveys/Analysis-Process-Methods.md ">Link</a>

Our respondents represent <b>diverse backgrounds</b> such as <b>38% are Platform Engineers, 26% are DevOps Engineers, 10% are Site Reliability Engineers, </b>and the remaining are <b>Software Developers and Cloud Engineers.</b> This shows our survey reached people from <b>many different roles</b>.

## Qualitative Highlights:

We asked engineers one <b>key question: "Why does your organization run multi-clusters?" And we discovered five common patterns.</b>

The <b>first common pattern is Infrastructure Provider.</b> Engineers deploy clusters across <b>cloud, on-premises, </b>or <b>edge locations.</b> This gives them <b>flexibility</b> and helps <b>avoid vendor lock-in.</b>
Second, Isolation. Teams <b>keep workloads</b> and <b>environments separate</b> for better <b>security</b> and easier <b>management.</b>
Third, Business Unit. <b>Each team gets their own cluster,</b> giving them <b>ownership</b> and making <b>compliance easier.</b>
Fourth, Region. Engineers deploy clusters across different geographic locations for <b>better performance</b> and <b>geo-redundancy</b>. If one region fails, others keep the system running.
And fifth, the <b>most common pattern is Environment separation.</b> Organizations separate <b>development, staging, and production</b> environments. This lets engineers <b>test safely without disturbing live systems.</b>
Let's move on to the next questions, which shows the key challenges engineers face in multi-cluster operations.Our user research identified four major challenge areas:<b>51% struggle with workload management, 39% with observability, 25% with operational complexity,10% with time management.</b>

Engineers struggle daily with cluster management such as <b>stateful workloads, upgrades, configurations, resource distribution, </b>and <b>multi-cluster complexity.</b>

Engineers  struggle to understand <b>what's happening across multiple clusters is very challenging</b> because <b>data is spread across multiple tools.</b> They also complain about <b>networking complexity.</b> During multi-cluster incidents, engineers follow <b>standard on-call</b> processes, but our research shows that <b>every alert feels unique to them</b>—even 
When <b>alerts look familiar</b>, the <b>context and impact</b> are always different. The real <b>bottleneck</b> is <b>situational awareness</b>. If they know which cluster, which service, and what the impact is, they can act with confidence.

Engineers reported challenges on operational complexity such as <b>context-switching, repetitive tasks, environment setup, missing zero-trust templates, limited team knowledge, and failover scenarios that require manual intervention</b>
Engineers lose countless hours on <b>repeated setups, slow deployments</b>, and <b>troubleshooting</b>. These challenges clearly show the difficulties engineers face when managing multi-clusters."

We asked engineers what they want in <b>future multi-cluster operations</b>. Three clear patterns emerged from research these are 

1. <b>AI & Automation</b> to handle <b>routine tasks</b> so engineers can focus on <b>high-priority</b> work, 

2. <b>Flexible Architecture</b> that adapts to different <b>deployment, performance,</b> and <b>cost needs,</b> 

3. <b>A simplified UX</b> with <b>easy to use dashboard</b> and <b>clear documentation</b> and <b>simplified workflows</b> —designed for everyone from new to experienced engineers to use with confidence."


User research also revealed two <b>uncommon</b> patterns such as <b>dashboard as code for functionality</b> and <b>specialized hardware for multi-cluster operations.</b> 
<b>One of our Platform Engineers, who manages more than 50 clusters, says that</b> “Multi-clusters provide practical solutions to organizational, technical, and cost-related limitations that a single cluster simply cannot address.” This statement explains that a multi cluster isn’t just a scaling choice. <b>But it’s a strategic evolution toward flexibility, resilience, and innovation.</b>

## Quantative Highlights:

## Key findings & Recommendations:

From the data analysis five user research areas emerged these are documentation gap, centralized monitoring, AI driven automation, Operational complexity, Developer UX. Let's see how our recommendations could improve these research areas.

<li>Review <b>multi-cluster project materials</b> to <b>identify what's missing or outdated. Create practical guides with real examples</b> and work with <b>SIG-Community</b> to <b>build tested documentation</b> for daily engineering work.</li>

<li>We recommend that to start by <b>identifying current tools, overlaps, and gaps</b> then create a <b>single observability system</b> with <b>common standards</b> for <b>logs, metrics,</b> and <b>data storage, network visibility, AI-connected alerts, and role-based dashboards.</b></li>

<li>We recommend AI and automation <b>taking over routine fixes</b> — systems that can predict problems before they happen and act on their own.</li>

<li>We recommend that <b>organizations</b> provide <b>hands-on training</b> in multi-cluster operations and <b>improve zero-trust principles</b> and <b>automation reliability,</b> and <b>encourage knowledge</b> sharing through <b>playbooks</b> and <b>peer learning to close skill gaps</b></li>

<li>Study how developers currently work to find what <b>slows them down</b> then use these study <b>insights to build developer friendly solutions</b> on multi cluster operations.</li>

The new engineer said, <b><i>“Make it easy.”</i></b>

Our research highlights that the future of multi-cluster management lies in <b>combining technical excellence with human-centered design. </b>

👉 Our research continues with the next step on generating the persona to mapping the workflows. 

