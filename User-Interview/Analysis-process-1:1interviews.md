<h2>Qualitative analysis Analysis process for 1:1 interviews:</h2>

This section provides detailed information about how we conducted the research analysis across key areas, including deployment, observability, and maintenance, as well as additional subcategories such as team collaboration, multi-tenancy, and the major challenges developers face when working in multi-cluster environments.
We will explain the entire analysis process using the deployment workflow as an example. We followed the same analysis process for observability, maintenance, and other subcategories as well.

<h2>How We Identified Common Deployment Patterns and Key Findings</h2>

We analyzed deployment workflows shared by <b>12 engineers</b> to understand how they manage Kubernetes multi-cluster deployments, what tools they use, where automation takes place, and what challenges they experience.
Our analysis followed six steps. 

<b>Individual Interviews → Workflow Documentation → Common Activities → Operational Journeys → Challenges → Key Findings → UX Opportunities</b>

<b>Step 1: Document Each Engineer's Workflow</b>

We started by reviewing each engineer's interview and documenting their deployment workflow step by step.
We focused on understanding:

- What activities engineers perform
- What tools they use
- Which steps are automated or manual
- How they validate deployments
- How they handle deployment failures

<b>Goal:</b> Understand each engineer's workflow before comparing it with others.

<b>Step 2: Identify Common Activities</b>

Next, we reviewed the workflows to identify activities that served similar purposes.

For example, engineers used different tools, such as Argo CD, Flux, and Helm, to deploy applications.
Although the tools were different, they supported a similar goal: executing application deployments.
We grouped these activities based on their purpose while keeping track of the differences in tools and implementation.

<b>Goal:</b> Find similarities across workflows, even when engineers use different technologies.

<b>Step 3: Identify the Common Operational Journey</b>

During our analysis, we identified common activities involved in managing Kubernetes clusters and deploying applications across multiple clusters.

We combined these activities into a single operational journey that covers cluster creation, configuration, application deployment, validation, maintenance, upgrades, and failure recovery.

We organized similar activities into common stages to provide a clear overview of the end-to-end workflow.

Although engineers used different tools and followed different processes, we focused on identifying shared activities and their purposes.

<b>Goal:</b> Create a unified operational journey that represents common activities and workflows identified across the 12 engineer interviews.

<b>Step 4:Identify Challenges and Manual Work</b>

We examined each workflow to understand where engineers experienced operational difficulties.

We looked for:

- Manual tasks and repetitive work
- Switching between different tools
- Dependencies between deployment steps
- Deployment validation requirements
- Failure handling and recovery activities
- Challenges coordinating across multiple clusters
- We separated challenges directly reported by engineers from potential issues identified during our analysis that would need further validation.

<b>Goal:</b> Understand where engineers face difficulties and where improvements may be needed.

<b>Step 5: Identify Recurring Patterns and Key Findings</b>

After comparing all 12 workflows, we identified recurring patterns and synthesized them into five key finding areas:

<b>Deployment Automation:</b> How automation is used and where manual work remains.

<b>Cross-Cluster Coordination:</b> How engineers manage deployments across multiple clusters.

<b>Health Validation:</b> How engineers verify that deployments are successful and applications are healthy.

<b>Operational Complexity:</b> Challenges caused by multiple tools, configurations, and processes.

<b>Failure Recovery:</b> How engineers detect, troubleshoot, and recover from deployment failures.

<b>Goal:</b> Turn individual workflow observations into broader research findings.

<b>Step 6: Identify UX Opportunities</b>

Finally, we used these findings to identify opportunities for improving the multi-cluster deployment experience.

The main opportunity areas included:

- Improving visibility into deployment progress across clusters
- Reducing repetitive manual tasks
- Making deployment validation easier
- Supporting better coordination across tools and clusters
- Helping engineers understand and respond to partial deployment failures

<b>Goal:</b> Translate research findings into potential UX improvements.

<b>Note</b>To respect participant consent and protect confidentiality, we will not share individual participants’ deployment workflows. Instead, we will present aggregated research findings, analysis, and key patterns identified across deployment workflows based on the raw research data.

