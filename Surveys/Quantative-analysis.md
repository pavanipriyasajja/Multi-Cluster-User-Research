## Quantitative analysis:

### Demographics
We began our analysis by understanding who our participants are and the roles they play in managing Kubernetes clusters. To do this, we asked: <b>“What is your primary role in managing Kubernetes clusters?”</b> This helped us establish the demographic context for interpreting the rest of the survey findings.

Participants selected from common industry roles such as DevOps Engineer, Platform Engineer, Site Reliability Engineer (SRE), Cloud Engineer, and Software Developer, along with an “Other” option to capture additional or hybrid roles. The responses revealed a diverse set of participants, including Platform Engineers, DevOps Engineers, Cloud Engineers, Software Developers, SREs, as well as roles like Managers, Architects, Platform Security Engineers, and System Administrators. We also observed several hybrid roles, such as engineers working across both DevOps and Platform Engineering functions.

To better understand the distribution, we analyzed the frequency of responses and converted them into percentages. The results showed that <b>Platform Engineers (39%)</b> and <b>DevOps Engineers (26%)</b> make up the majority of respondents, followed by <b>SREs (9%), Software Developers (8%),</b> and <b>Cloud Engineers (7%).</b>

This distribution highlights that multi-cluster management is not owned by a single role. Instead, it spans across multiple disciplines within engineering teams. While Platform and DevOps Engineers form the core group, the presence of SREs, developers, and other specialized roles indicates that responsibilities are shared, often requiring cross-functional collaboration.

These findings led us to identify <b>“Demographics”</b> as a key quantitative theme in our analysis. Understanding who is involved in multi-cluster operations provides essential context for the rest of the research, as each role brings different priorities, workflows, and challenges when working with Kubernetes at scale.

### Cluster Deployment Frequency

As a next step, we wanted to understand the scale at which engineers operate in multi-cluster environments. To explore this, we asked: <b>“How many clusters do you manage or deploy to currently (per month)?”</b> This question helped us capture both the frequency and scale of interaction engineers have with Kubernetes clusters.

Participants selected from four ranges: 1–3, 4–10, 11–50, and 50+ clusters per month. During analysis, we observed that the 1–3 and 4–10 categories represented relatively smaller-scale operations. To simplify interpretation and better highlight broader trends, we combined these into a single group representing <b>1–10 clusters per month.</b>

This allowed us to analyze the data across three clearer segments: <b>1–10 clusters, 11–50 clusters,</b> and <b>50+ clusters per month.</b> The results showed that <b>45% of engineers manage 1–10 clusters per month,</b> while <b>33% manage between 11–50 clusters, </b>and <b>22% manage more than 50 clusters monthly.</b>

One of the most notable insights is that a majority of respondents <b>55% are working with more than 10 clusters per month,</b> indicating a strong presence of medium to large-scale multi-cluster operations. This highlights that multi-cluster management is not limited to small-scale use cases, but is widely adopted across more complex and demanding environments.

These findings suggest that engineers are actively managing and deploying clusters at scale, reinforcing that multi-cluster operations are both a <b>common and growing practice.</b> The variation in scale also points to differing levels of operational complexity, which has direct implications for tooling, scalability, monitoring, and overall efficiency.

This pattern provides important context for the rest of the research, especially when understanding the challenges engineers face in managing distributed systems across multiple clusters.

### Cluster Deployment Environments

To better understand the environments in which Kubernetes clusters are deployed, we asked: <b>“Where are your clusters deployed? (Select all that apply)”. </b>This question helped us capture the diversity of infrastructure setups used in multi-cluster operations.

Since participants could select multiple options, this allowed us to see how engineers combine different environments rather than relying on a single deployment model. The responses included setups such as single cloud providers (e.g., AWS, Azure, GCP), multi-cloud, on-premise data centers, hybrid environments, edge locations, and other specialized configurations.

The results highlight a highly diverse and distributed infrastructure landscape. <b>48.8% of engineers reported using a single cloud provider</b>, indicating that many organizations still rely on a centralized cloud environment. At the same time, <b>44.7% reported using on-premise data centers,</b> showing that traditional infrastructure continues to play a significant role in multi-cluster strategies. We also observed that <b>30.6% of respondents are operating in multi-cloud</b> environments, reflecting a growing need for flexibility, redundancy, and vendor diversification. Additionally, <b>26.5% reported working in hybrid environments</b>, combining cloud and on-premise systems often to integrate legacy infrastructure with modern cloud platforms. A very small proportion <b>(0.6%) indicated more specialized setups</b>, such as bare metal on rented servers.

Because this was a multi-select question, the total exceeds <b>100%, reinforcing an important insight: many engineers are managing clusters across multiple environments simultaneously.</b>

Overall, these findings show that multi-cluster deployments are inherently <b>multi-environment.</b> Organizations are not only adopting cloud-native approaches but are also blending them with on-premise and hybrid infrastructures. This diversity introduces additional layers of complexity, particularly in terms of cluster management, integration, and observability.

A <b>key pattern</b> that emerged is that engineers are <b>consistently deploying clusters across multiple and diverse infrastructure providers, rather than operating within a single environment.</b> This reflects the evolving reality of Kubernetes adoption, where flexibility and distribution are essential.

These <b>insights</b> point to a growing need for solutions that can <b>provide consistent management, visibility, and interoperability across environments, helping engineers effectively manage the increasing complexity of multi-cluster systems.</b>

### Cluster Tenancy Model

To understand how Kubernetes clusters are shared and managed across teams, we asked: <b>“What is the typical tenancy model of your clusters?”. </b>This question helped us explore whether clusters are dedicated to single teams, shared across multiple teams, or used in a combination of both models.

Participants selected from options including mostly single-tenant, mostly multi-tenant, a mix of both, and not sure/prefer not to say. The responses reveal a clear trend toward shared and flexible cluster usage.

The most common model is multi-tenancy, with <b>44%</b> of engineers reporting that they primarily use <b>multi-tenant</b> clusters. This suggests that many organizations are prioritizing resource efficiency by allowing multiple teams or workloads to share the same cluster infrastructure.

In addition, <b>32.9%</b> of respondents reported using a mix of both <b>single-tenant and multi-tenant models, </b>indicating a <b>hybrid approach</b>. This reflects how teams <b>balance the need for isolation with the benefits of shared resources,</b> often adapting their strategy based on workload requirements or organizational constraints.

A smaller segment, <b>20.6% </b>of engineers, reported using mostly <b>single-tenant clusters,</b> suggesting that some organizations still prioritize dedicated environments typically for reasons such as security, compliance, or strict workload isolation. Only a minimal number of respondents selected “not sure,” indicating that most participants have a clear understanding of their tenancy model.

Overall, the findings show that <b>multi-tenant and hybrid approaches dominate</b>, with <b>76.9% </b> of engineers working in either shared or mixed tenancy environments. This reflects a broader shift toward optimizing resource utilization while maintaining flexibility in how clusters are allocated and managed.

At the same time, this <b>shift introduces additional complexity</b>. Managing shared environments requires careful consideration of access control, security boundaries, and workload isolation. The presence of hybrid models further highlights that organizations are actively balancing flexibility with control, tailoring their approach based on evolving needs.

A key pattern that emerges is that <b>cluster tenancy models are increasingly shifting toward shared and hybrid environments across teams. </b>This reinforces the growing importance of solutions that can support secure, scalable, and efficient multi-tenant operations in modern multi-cluster ecosystems.

### Multi-Cluster Tools Usage

To understand which tools engineers rely on for managing multi-cluster environments, we asked: <b>“Which of the tools below do you, or other people on your team, use frequently and rely on for multi-cluster operations?” (Select all that apply).</b> This question was designed to uncover tool adoption patterns across different scales of cluster usage and team practices.

Participants selected from a broad ecosystem of tools, including Argo CD, Flux CD, Rancher, Custom Controllers, OpenShift ACM, Karmada, Istio, Thanos, Kyverno, OPA Gatekeeper, and others. We also included an option for engineers who do not use any dedicated multi-cluster tools.

To better understand how tooling choices vary, we analyzed responses across different cluster deployment scales: <b>1–10 clusters, 11–50 clusters, and 50+ clusters per month.</b> Clear patterns emerged across these groups.

For smaller-scale environments (1–10 clusters), engineers tend to rely on widely adopted, ready-to-use tools such as <b>Argo CD</b> and <b>Rancher</b>, which provide simplicity and efficiency for managing a limited number of clusters. As the scale increases (11–50 clusters), tools like <b>Argo CD</b> remain common, but we begin to see a stronger adoption of <b>Custom Controllers,</b> indicating a need for more tailored automation.

At the <b>largest scale (50+ clusters),</b> the pattern shifts significantly. Engineers managing large, complex environments primarily rely on <b>Custom Controllers,</b> supplemented by tools such as <b>Kyverno, Thanos, and Flux CD.</b> This reflects a move toward more advanced, customizable solutions to handle increased operational complexity.

Across all cluster sizes, <b>Custom Controllers emerged as one of the most consistently adopted approaches</b>, highlighting their importance in enabling flexibility and automation in multi-cluster operations. At the same time, a small portion of respondents reported not using any dedicated tools, suggesting that some teams still rely on manual processes or internal solutions.

A key insight from this analysis is that <b>tool usage strongly correlates with cluster scale.</b> Engineers working with smaller deployments tend to favor standardized tools that are easy to adopt and operate, while those managing large-scale environments increasingly depend on custom-built or advanced solutions to meet their needs.

These findings highlight the diversity of the multi-cluster tooling ecosystem and reinforce that <b>there is no single tool that fits all use cases.</b> Instead, <b>organizations adopt a mix of standardized and custom solutions based on their scale, complexity, and operational requirements.</b>

Overall, this pattern shows that <b>multi-cluster operations are supported by a combination of widely adopted tools and custom-built solutions,</b> with tool choice heavily influenced by deployment scale. This underscores the need for flexible, scalable, and interoperable tooling that can support engineers across a wide range of multi-cluster environments.

### Challenges in Using Multi-Cluster Tools

To understand the challenges engineers face when working with multi-cluster environments, we asked: <b>“What challenges have you experienced when using multi-cluster tools?”.</b> This question aimed to capture pain points across the full lifecycle of multi-cluster operations, including setup, day-to-day management, and long-term maintenance.

Participants were able to select multiple challenges, allowing us to capture a broad and realistic picture of the issues engineers encounter. The responses reveal a strong concentration around <b>operational complexity and observability,</b> followed by concerns related to security, networking, and system integration.

The most frequently reported challenge is <b>complexity in setup and configuration, </b>selected by <b>59.4% of respondents.</b> This highlights that getting started with multi-cluster systems and maintaining them over time remains a significant barrier for many engineers. Closely following this, <b>48.8% of respondents reported challenges with observability and debugging across clusters,</b> reflecting the difficulty of monitoring and troubleshooting distributed systems.

Security and access management also emerged as major concerns, with <b>40 % of engineers reporting challenges related to multi-tenancy isolation and access control.</b> In shared environments, ensuring proper boundaries between teams and workloads remains a critical and complex task. Additionally, <b>35.3% of respondents highlighted networking and service discovery issues,</b> indicating the difficulty of enabling reliable communication between clusters.

A second layer of challenges points to gaps in usability and ecosystem maturity. <b>28.8% of respondents reported a lack of clear documentation and integration issues with cloud and on-premise environments,</b> suggesting that engineers often struggle to understand and connect different parts of the multi-cluster ecosystem. Similarly, <b>27.1% reported challenges with policy enforcement across clusters,</b> reflecting difficulties in maintaining consistent governance.

Other concerns, while less frequently selected, still represent meaningful friction points. These include <b>limited support or community activity (22.4%)</b> and <b>scalability challenges (21.8%).</b> Only a small number of respondents reported having no major challenges, reinforcing that most engineers encounter at least one difficulty when working with multi-cluster tools.

Overall, these findings make it clear that <b>multi-cluster operations are inherently complex.</b> The combination of setup overhead, limited visibility across clusters, and challenges in managing shared environments creates a steep learning curve and ongoing operational burden.

A key pattern that emerges is that <b>engineers consistently face challenges related to setup complexity, observability, and multi-tenancy management.</b> These issues highlight critical areas where improvements are needed particularly in simplifying configuration, enhancing cross-cluster visibility, and strengthening security and access controls.

These insights underscore the importance of building <b>robust, user-friendly, and well-supported multi-cluster solutions</b> that can reduce operational complexity while improving reliability, scalability, and <b>overall developer experience.</b>

### Metrics Tracked Across Clusters

To understand how engineers monitor and maintain multi-cluster environments, we asked: <b>“What metrics do you track most frequently across clusters?”.</b> This question aimed to identify the key signals engineers rely on for performance, reliability, and operational visibility.

Participants were able to select multiple options, which allowed us to capture a realistic view of monitoring priorities. The results show a strong concentration around <b>core operational and reliability metrics,</b> with a noticeable gap between the most critical metrics and the rest.

The most frequently tracked metric is <b>CPU and memory utilization,</b> selected by (141) <b>82.9% of respondents</b>, indicating that resource usage remains the primary focus when managing clusters. This reflects the importance of capacity planning and efficient resource utilization in distributed environments.

Closely following this, (133)<b> 78.2% of engineers track pod health and readiness,</b> highlighting the need to ensure workloads are functioning correctly and remain stable across clusters. <b>Service availability</b> is also a top priority, selected by <b>71.2% of respondents,</b> emphasizing the critical importance of uptime and reliable service delivery.

Together, these three metrics form a dominant group, clearly standing out as the foundation of multi-cluster monitoring practices.

Other metrics, while still relevant, are tracked less frequently. <b>Persistent volume usage (31.8%)</b> shows moderate attention to storage monitoring, while <b>policy compliance (27.1%)</b> indicates that governance is considered but not consistently prioritized. Similarly, <b>network latency between clusters (27.1%)</b> is tracked by fewer respondents, suggesting that cross-cluster networking visibility is either more challenging to implement or less emphasized in current workflows.

Overall, these findings indicate that engineers primarily focus on <b>core system performance and application reliability</b> when managing multi-cluster environments. Metrics related to resource utilization, workload health, and service uptime are well-established and widely adopted.

At the same time, the lower emphasis on areas such as network latency and policy compliance points to potential gaps whether in tooling, visibility, or prioritization. These areas may represent opportunities for improvement, particularly as multi-cluster environments grow in scale and complexity.

A key pattern that emerges is that <b>engineers prioritize foundational performance and reliability metrics over more advanced or cross-cluster insights.</b> This highlights that while basic monitoring practices are mature, there is still room to enhance visibility into more complex aspects of multi-cluster operations.

### Root Cause Identification Across Clusters 

To understand how engineers diagnose issues in distributed environments, we asked: <b>“How do you identify the root cause of a workload issue when it spans multiple clusters?”</b>. This question aimed to explore the tools and approaches used for troubleshooting and root cause analysis in multi-cluster setups.

Participants were able to select multiple methods, providing a comprehensive view of how teams approach debugging across clusters. The responses reveal a strong reliance on <b>foundational observability signals and manual investigation techniques.</b>

The most commonly used method is <b>logs,</b> selected by <b>82.4% of respondents,</b> indicating that log analysis remains the primary approach for diagnosing issues. This is followed by <b>metrics (71.2%),</b> which play a key role in identifying performance and system-level anomalies. Together, logs and metrics form the backbone of troubleshooting practices in multi-cluster environments.

In addition, <b>68.2% of engineers reported relying on manual investigation,</b> highlighting that hands-on debugging and experience-driven analysis are still essential parts of the process. <b>Alerts (62.9%)</b> are also widely used, helping engineers detect and respond to issues in real time.

More advanced techniques, however, are used less frequently. <b>Network tracing is utilized by only 25.3% of respondents,</b> despite its importance in understanding distributed systems. Even more notably, <b>automated diagnostic tools are used by just 12.9%, </b>indicating that <b>automation in root cause analysis is still relatively limited.</b>

Overall, these findings suggest that troubleshooting in multi-cluster environments is largely <b>manual and reactive,</b> with engineers relying heavily on core telemetry data such as logs and metrics. While these methods are effective, they often require significant effort and expertise to correlate signals across clusters.

The high reliance on manual investigation points to a <b>lack of fully integrated or automated diagnostic workflows,</b> while the low adoption of advanced tools highlights an opportunity to improve efficiency and reduce operational overhead.

A key pattern that emerges is that <b>engineers depend primarily on logs, metrics, and manual investigation for root cause analysis, with limited use of automated and advanced diagnostic solutions.</b> This reflects a broader gap in automation and integrated observability.

These insights emphasize the need for <b>more advanced, user-friendly, and integrated troubleshooting solutions </b>that can simplify root cause analysis and improve efficiency in complex multi-cluster environments.

### Most Useful Alerts in Multi-Cluster Environments

To understand which alerts are most valuable for monitoring and maintaining multi-cluster systems, we asked: <b>“What kind of alerts do you find most useful in a multi-cluster setup?”.</b> This question aimed to identify the alerting signals engineers rely on to detect issues and respond effectively.

Participants were able to select multiple alert types, giving us a broad view of alerting priorities across multi-cluster environments. The responses show a clear preference for <b>workload-level and system health alerts</b>, which are critical for maintaining reliability.

The most commonly selected alert type is <b>pod crashes or restarts</b>, chosen by <b>71.8% of respondents, </b>indicating that workload stability is the top priority for engineers. This is followed by <b> cluster health degradation alerts (60.6%),</b> which highlight the importance of monitoring the overall condition and performance of clusters.

Another key alert type is <b> API server unresponsiveness (42.4%), </b>reflecting concerns around control plane reliability and availability. Ensuring that the cluster control plane remains responsive is essential for maintaining operational continuity.

Other alert types, while still relevant, are less frequently prioritized. <b>Inter-cluster network issues (35.3%) </b>indicate the need to monitor communication between clusters, while <b>inconsistent workload placement (23.5%)</b> points to challenges in scheduling and distributing workloads effectively across environments.

Overall, these findings suggest that alerting strategies in multi-cluster environments are primarily focused on <b>immediate operational issues that directly impact application reliability. </b>Engineers prioritize signals that help them quickly detect failures and maintain system stability.

The strong emphasis on pod-level and cluster health alerts highlights a reactive approach centered around identifying and resolving failures as they occur. In contrast, the lower emphasis on networking and workload distribution alerts may indicate gaps in visibility, limitations in tooling, or lower prioritization of these more complex aspects of multi-cluster operations.

A key pattern that emerges is that <b>engineers prioritize workload stability and cluster health alerts, with comparatively less focus on cross-cluster networking and workload distribution issues.</b>

This highlights that while core reliability monitoring is well-established, there is an opportunity to evolve alerting strategies to better support complex, distributed, multi-cluster environments particularly in areas that require deeper cross-cluster visibility and coordination.

### Expectations from a Centralized Observability Dashboard

To understand what engineers expect from a centralized observability solution, we asked: <b>“What would you want from a centralized observability dashboard for multiple clusters?”.</b> This question aimed to identify the most valuable features and capabilities needed to effectively monitor and manage multi-cluster environments.

Participants were able to select multiple features, providing insight into the most desired capabilities for a centralized observability dashboard. The responses reveal a strong preference for <b>unified visibility, real-time monitoring, and flexible customization.</b>

The most requested feature is a <b> unified view of workload health,</b> selected by <b>80.6% of respondents, </b> highlighting a critical need for a single pane of glass across clusters. This reflects the ongoing challenge of fragmented visibility in distributed environments.

This is followed by<b> real-time alerts and incident tracking (64.1%), </b> emphasizing the importance of quickly detecting and responding to issues. Similarly, <b>cross-cluster log aggregation (57.6%)</b> stands out as a key requirement, reinforcing the need for centralized logging to simplify troubleshooting across clusters.

Flexibility also plays a major role in tool expectations. <b>53.5% of engineers indicated a need for customizable queries and dashboards,</b> suggesting that one-size-fits-all solutions are often insufficient for diverse operational workflows.

Additional features, while slightly less prioritized, still provide important context. These include <b>prebuilt dashboards with minor adjustments (48.8%), automated issue detection or root cause analysis (48.2%), </b>and <b>policy compliance and security monitoring (44.1%).</b> A smaller portion of respondents <b>(39.4%) </b>preferred fully out-of-the-box dashboards with no customization required.

Overall, these findings indicate that engineers are looking for <b>centralized, flexible, and actionable observability solutions. </b>The strong demand for unified workload visibility highlights the need to reduce fragmentation across clusters, while the emphasis on real-time alerts and log aggregation underscores the importance of faster detection and resolution of issues.

The preference for customizable dashboards over fully predefined solutions suggests that engineers value adaptability, allowing them to tailor observability tools to their specific environments and workflows. At the same time, the growing interest in automated diagnostics points to an emerging demand for more intelligent, automation driven observability though adoption in this area is still evolving.

A key pattern that emerges is that <b>engineers prioritize unified visibility, real-time monitoring, and customization, with a growing interest in automation and intelligent diagnostics.</b>

These insights highlight the need for <b>centralized observability platforms that combine visibility, flexibility, and automation, </b> enabling engineers to effectively manage the increasing complexity of multi-cluster systems.

### Preferred Automated Responses for Cross-Cluster Issues

To understand how engineers want to handle issues across multiple clusters, we asked: <b>“Which types of automated responses would you like to see for handling cross-cluster issues?”. </b>This question aimed to identify preferences for automation in improving reliability, scalability, and overall operational efficiency in multi-cluster environments.

Participants were able to select multiple options, giving us insight into the types of automation engineers find most valuable. The responses show a strong preference for <b>automated remediation and scaling capabilities,</b> particularly those that directly impact system reliability.

The most preferred option is <b>automated failover, </b>selected by <b>62% of respondents,</b> highlighting the importance of maintaining high availability during failures. This reflects the critical need for systems that can automatically recover from disruptions without requiring immediate manual intervention.

Closely following this, <b>auto-scaling based on workload health (55.8%) </b>emerged as another key priority, indicating that engineers value dynamic resource management that can adapt to changing workloads and maintain performance.

At the same time, <b>41.1% of respondents selected alert escalation without automatic action, </b>suggesting that many teams still prefer a level of human oversight. This indicates a balanced approach, where automation is used for detection and notification, but final decision-making may still involve engineers.

Additionally, <b>36.8% of respondents expressed interest in policy-based workload redistribution, </b>reflecting a need for automated workload balancing across clusters to improve efficiency and resilience.

Only a small portion <b>(12.9%) </b>indicated a preference for fully manual intervention, suggesting that most engineers are open to <b>adopting automation in their workflows.</b>

Overall, these findings indicate that engineers are increasingly comfortable with automation, especially for tasks that improve <b>system reliability and scalability. </b>The strong interest in automated failover and auto-scaling highlights the need for systems that can respond quickly to failures and dynamically adjust to demand.

At the same time, the continued reliance on alert-based escalation shows that <b>human-in-the-loop models remain important, </b>allowing teams to maintain control over critical decisions while still benefiting from automation.

A key pattern that emerges is that <b>engineers prefer automation for reliability and scalability, while maintaining selective human oversight in decision-making.</b>

These insights point to a growing demand for <b>intelligent, controlled automation</b> in multi-cluster environments solutions that can act autonomously when needed, while still enabling engineers to intervene when necessary.
















