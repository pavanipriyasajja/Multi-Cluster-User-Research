<h2>Observability analysis:</h2>

During the interviews, we asked participants about their troubleshooting processes and challenges to better understand their workflows, pain points, and difficulties in identifying and resolving issues.

<h2>Patterns identified from Troubleshooting workflows </h2>

Here are the list of patterns identified form the participants.

<b>Theme : 1 Observability-first</b> 

In this pattern, engineers begin troubleshooting through monitoring and observability systems. They investigate abnormal behavior using dashboards, alerts, logs, metrics, and other runtime information before accessing Kubernetes resources directly.

<b>Monitoring → Dashboard → Logs → Recent changes → Cluster → Root cause → Fix</b>

Monitoring may reveal abnormal behavior without explaining the underlying cause. Engineers need to correlate multiple signals and may have to move into Kubernetes or infrastructure investigation.

<b>Theme : 2 Deployment-driven troubleshooting</b>

Some engineers begin troubleshooting when a deployment fails, a CI process reports an issue, or an application behaves unexpectedly after a change.

Rather than starting with overall cluster health, they investigate the deployment and its runtime behavior.

<b>Deployment or CI failure → Identify affected service/deployment → Check deployment status → Review runtime signals → Investigate configuration or application changes → Resolve</b>

Engineers need to understand the relationship between deployment changes and runtime failures. Deployment information and observability data may be available in different systems.

<b>Theme : 3 Cluster-level manual troubleshooting</b>

When monitoring tools do not provide enough information, engineers directly investigate Kubernetes resources. This pattern involves progressively moving from workload-level information into lower-level infrastructure details.

<b>Alert → Identify cluster → kubectl → Inspect pods → Check events → Investigate nodes → Review logs → Investigate host or infrastructure → Fix</b>

Engineers need knowledge of Kubernetes resources and infrastructure. Investigation requires moving between multiple levels of the system. Some incidents require direct cluster access or elevated permissions. High-level monitoring may not explain complex failures.

<b>Theme : 4 Cross-cluster comparison</b>

Engineers compare clusters when an application or workload behaves differently across environments. This is particularly relevant in multi-cluster Kubernetes environments because the same application may operate successfully in one cluster while failing in another.

<b>Identify affected cluster → Find comparable healthy cluster → Compare environments → Investigate differences → Narrow possible causes → Resolve</b>

Cluster A (Healthy) ≠ Cluster B (Unhealthy)

Engineers manually inspect multiple environments and determine which differences may be related to the incident.

<b>Theme : 5 Developer portal and GitOps-driven troubleshooting</b> 

Some engineers use internal developer portals and GitOps tools as their initial troubleshooting interface. Rather than immediately connecting to Kubernetes clusters, they first examine the application or environment through a higher-level abstraction.

<b>Alert/deployment issue → Identify environment → Open developer portal → Check application health → Open Argo CD → Review deployment/resource status → Investigate observability signals</b>

A developer portal may show whether an application is healthy without providing all the information needed to explain the failure. Engineers may need to move into specialized monitoring or Kubernetes tools.

<b>Theme : 6 Fleet-level troubleshooting and blast-radius assessment</b> 

In this pattern, engineers begin by determining the scope of the incident across multiple clusters. Instead of immediately troubleshooting one affected cluster, they investigate whether the same issue appears elsewhere.

<b>Receive alert → Identify affected cluster(s) → Determine fleet impact → Investigate common factors → Identify root cause → Apply controlled remediation</b>

Engineers need to distinguish an isolated cluster failure from a shared problem involving multiple clusters. They must also understand the potential impact of changes made during recovery.

<b>Theme : 7 Deep infrastructure and network troubleshooting</b> 

Some incidents cannot be diagnosed through application logs or standard monitoring alone. Engineers investigate lower-level network, infrastructure, and identity-related information.

<b>Detect issue → Review application/cluster telemetry → Investigate service communication → Inspect network information → Capture traffic or compare configurations → Identify underlying failure</b>

Standard logs and metrics may not explain network-related failures. Engineers need specialized tools and technical expertise. Some infrastructure or control-plane information may be less visible. Centralized monitoring may be insufficient during connectivity failures.

<b>Theme : 8 Automated self-healing and escalation</b>  

Some organizations rely on automated systems to detect and recover from known failures before involving engineers. Human intervention becomes necessary when automation cannot resolve the incident.

<b>Monitoring detects issue → Automated self-healing → Check recovery → If unresolved, alert on-call engineer → Escalate to specialist when necessary</b>

Automated remediation cannot resolve every failure. Complex incidents still require manual investigation and expert knowledge.

<b>Theme : 9 AI-assisted troubleshooting</b> 

Some engineers use AI-assisted tools to help investigate Kubernetes incidents, gather context, and identify possible causes. However, AI assistance does not necessarily mean automated remediation.

<b>Detect issue → Gather application and Kubernetes context → Use AI-assisted investigation → Review findings → Engineer decides next action → Apply fix</b>
One participant expressed concern about allowing AI tools to make unintended changes and therefore kept the tool in manual mode.

<b>Theme: 10 Cluster rebuild and replacement</b>

For certain severe failures, engineers may choose to replace an unhealthy cluster rather than continue attempting to repair it.

<b>Detect unhealthy cluster → Assess severity → Remove cluster from traffic → Preserve information if needed → Delete/rebuild cluster → Restore service → Validate health</b>

Engineers must make decisions about whether continued investigation or replacement is the more practical recovery strategy. Service continuity and recovery validation are important.

<b>Theme : 11 Progressive recovery and validation</b>
Engineers apply changes gradually across clusters to reduce the risk of introducing failures throughout the fleet. They validate cluster health after each stage before proceeding.

<b>Identify fix → Apply to selected cluster → Validate health → Continue to next cluster → Stop if unhealthy → Investigate and correct</b>
A change that works in one environment may not work everywhere. Engineers need to detect problems before they propagate to additional clusters.

<h2>Common Troubleshooting process</h2>

Although participants used different technologies, seven common stages emerged.

<b>Stage 1 : Detect the Issue</b> 

Troubleshooting begins with an indication that something is wrong. (Signals included: Monitoring alerts, Prometheus alerts, PagerDuty, CI failures, Deployment failures, User reports, Slack messages, Unexpected application responses, Abnormal cluster behavior)

There is no single entry point into troubleshooting., The first indication of an incident can originate from the observability system, deployment pipeline, application, or end user.

<b>Stage 2 : Identify the Scope</b> 

After receiving a signal, engineers try to determine: Where is the problem occurring, and how widespread is it?, (They identify:- Application/service, Environment, Namespace, Cluster, Region, Affected workload, One versus multiple clusters)

In multi-cluster incidents, another important question appears: Are other clusters experiencing the same problem?
Scope identification becomes more important in multi-cluster environments because engineers need to understand the blast radius, not simply locate one unhealthy resource.

<b>Stage 3: Assess Initial Health</b> 

Once the affected environment is identified, engineers typically perform a quick health assessment. Common starting points included: Dashboards, Developer portals, Argo CD, Kubernetes monitoring, Deployment status, Application health, Cluster health, Pod/workload health

Argo CD appeared repeatedly as an initial diagnostic point, although it was often only the beginning of the investigation. Engineers prefer to begin with a high-level health view before moving into deeper technical diagnostics.

<b>Stage 4 : Gather Observability Evidence</b> 

If the initial health view does not explain the problem, engineers gather additional evidence. Signals included: Application logs, Kubernetes logs, Metrics, Distributed traces, Kubernetes events, CPU usage, Memory usage, Disk usage, Network telemetry, Deployment state, Infrastructure status, Service-mesh information. 

Participants often have significant observability information available. The difficulty is frequently connecting the information, rather than simply collecting more telemetry.

<b>Stage 5 : Isolate the Root Cause</b>

When standard observability does not explain the failure, investigation becomes progressively deeper.
A common drill-down pattern was: <b>Application → Workload → Pod → Events → Node → Host/Infrastructure</b>
For network-related problems, investigation could continue into: <b>Service communication → Network telemetry → Packet capture</b>

Engineers also investigate: Recent code changes, Configuration changes, Network policies, Dependencies, Infrastructure changes, Certificates, Tokens, Identity/signatures, Permissions

Complex troubleshooting still requires substantial manual reasoning and domain expertise. Observability may identify the symptom without directly explaining the underlying cause.

<b>Cross Cluster comparison</b>

One particularly important multi-cluster behavior emerged. When an application works in one cluster but fails in another, engineers compare the environments.
The reasoning becomes: <b>Healthy Cluster A ↔ Unhealthy Cluster B</b>

Engineers look for differences in: Configuration, Networking, Dependencies, Infrastructure, Permissions, Certificates, Application behavior, Recent changes

Cross-cluster comparison is an important troubleshooting technique, but much of this comparison appears to be performed manually. The engineer is essentially trying to answer: <b>"What is different about the failing cluster?"</b>

<b>Stage 6 : Mitigation and Recovery</b> 

Participants demonstrated several different recovery strategies.
Manual recovery: Engineer identifies the problem and manually changes the affected resource or configuration.
Emergency intervention: Some failures require elevated permissions or direct infrastructure access.
Automated self-healing: In more automated environments (Alert → Self-healing → Automated remediation) The on-call engineer becomes involved only if remediation fails.

Rebuild instead of repair : participant described severe cluster failures where rebuilding was faster than continuing diagnosis (Remove from traffic → Save snapshot if needed → Delete cluster → Rebuild → Restore) 

Controlled fleet recovery : Infrastructure changes can be rolled out progressively (Cluster 1 → Change → Validate → Cluster 2 → Change → Validate)
If a cluster becomes unhealthy: <b>Stop rollout → Investigate → Fix → Continue</b>

Recovery strategies vary substantially according to infrastructure design and automation maturity. However, at multi-cluster scale, recovery introduces an additional concern:How can engineers restore service without spreading the failure?

<b>Stage 7 :Validate Recovery</b> 

Troubleshooting does not end when a change is made. Engineers need to confirm: Cluster is healthy, Application is healthy, Workloads recovered, Alerts cleared, Dependencies are functioning, Other clusters remain healthy, It is safe to continue a rollout

Observability serves two purposes: Detecting failures and confirming successful recovery. Fleet-wide validation becomes especially important when changes are being applied across multiple clusters.


<h2>Observed biggest challenge</h2> 

In Kubernetes multi-cluster environments, troubleshooting becomes more complex because engineers must identify which cluster is affected, whether the issue impacts one or multiple clusters, what differences exist between clusters, whether a shared change caused the issue, and the potential blast radius (scope of impact) across the environment.

<b>Which cluster? → One or many? → What's different between clusters? → Is there a shared change? → What's the blast radius?</b>

<h2>Key insights: </h2>

<b>Insight: 1 Fragmented observability</b>
Engineers rely on multiple monitoring, deployment, and infrastructure tools to investigate incidents. Relevant information is distributed across these systems, requiring engineers to manually gather and connect observability signals.

<b>Insight : 2 Limited fleet-wide visibility</b>
Engineers need to identify whether an incident affects a single cluster or multiple clusters. Understanding the scope and blast radius requires additional investigation when fleet-level health information is not immediately available.

<b>Insight: 3 Manual root-cause investigation</b>
Monitoring tools help engineers identify symptoms, but complex failures often require deeper investigation into workloads, Kubernetes events, nodes, networking, configuration, and infrastructure. Engineers manually correlate information to isolate the underlying cause.

<b>Insight: 4 Manual cross-cluster comparison</b>
When the same application behaves differently across clusters, engineers compare healthy and unhealthy environments to identify relevant differences. This process can require manual inspection of configurations, networking, dependencies, permissions, and infrastructure.

<b>Insight : 5 Complex recovery and validation</b>
Engineers use different remediation strategies, including manual fixes, self-healing, gradual rollouts, and cluster rebuilds. In multi-cluster environments, recovery must also consider the risk of affecting additional clusters and the need to validate health before continuing operations.








