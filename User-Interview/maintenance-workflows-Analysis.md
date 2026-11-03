<h2>Maintenance workflow Analysis</h2>

Through our research, we identified common maintenance workflows, engineers’ challenges, happy paths versus challenging paths, and key pain points and breakdowns at each stage of the workflow.

<h3>Stage 1 : Monitor and detect maintenance needs</h3>

<b>Activities observed:</b> Engineers check monitoring alerts, Slack notifications, incidents, security reports, available updates, and capacity signals. Some maintenance is triggered by developers reporting unexpected behavior.

<b>Automation involvement:</b> Scheduled checks, alerts, update notifications, automatic scaling, and some automated issue resolution.

<b>Human involvement:</b> Engineers review notifications, investigate unresolved alerts, determine urgency, and prioritize maintenance work.

<b>Where the workflow can break </b>

Maintenance signals are distributed across different tools, making it harder to build one complete view of what needs attention. Recurring or noisy alerts may require manual review and improvement.

<b>Challenge:</b> Identifying which signals are actionable and which clusters need immediate attention.

<b>Engineer goal:</b> Identify clusters, components, or infrastructure that require maintenance or attention.

<b>Opportunity:</b> A unified maintenance inbox showing cluster alerts, pending updates, incidents, and priorities.


<h3>Stage 2 : Assess changes, compatibility, and risk</h3>

<b>Activities observed:</b> Review component versions, release changes, security requirements, compatibility, and potential risks.

<b>Automation involvement:</b> Update detection and security notifications provide inputs to the assessment.

<b>Human involvement:</b> Engineers decide whether to proceed, defer, or investigate further. They evaluate the possible impact on existing environments.

<b>Where the workflow can break</b>

When compatibility or impact is unclear, engineers may need additional investigation before they can safely proceed. Unsupported updates can also require manual handling.

<b>Challenge:</b> Understanding the consequences of a change across components and clusters.

<b>Engineer goal:</b> Understand whether a maintenance change is necessary, safe, and compatible with the environment.

<b>Opportunity:</b> A change-impact view that shows affected clusters, component dependencies, compatibility concerns, and potential risks.

<h3>Stage 3 : Prepare and configure the maintenance change</h3>

<b>Activities observed:</b> Engineers update Terraform configurations, prepare upgrade bundles, modify component definitions, or create Git changes.

<b>Automation involvement:</b> Infrastructure-as-code tooling and automated workflows support repeatable configuration and deployment preparation.

<b>Human involvement:</b> Engineers define the desired changes, update configuration files, and handle unsupported or environment-specific requirements.

<b>Where the workflow can break</b>

One participant described inconsistent change tracking and Vault configuration changes that might not be committed to Git. This can make the actual environment difficult to reconcile with recorded configuration.

<b>Challenge:</b> Maintaining accurate and consistent configuration records across clusters.

<b>Engineer goal:</b> Prepare the infrastructure or component changes required for maintenance.

<b>Opportunity:</b> Configuration-drift visibility and clearer identification of changes made outside standard Git workflows.

<h3>Stage 4 : Review and approve changes</h3>

<b>Activities observed:</b> Engineers create, review, and merge pull requests. Some workflows require approval before pipeline execution.

<b>Automation involvement:</b> Git-based workflows and pipeline checks can support the review process.

<b>Human involvement:</b> Reviewers evaluate proposed changes, request corrections, and approve changes when appropriate.

<b>Where the workflow can break</b>

The workflow may wait for review, approval, or corrections. This is a potential handoff delay, although the participant summaries do not establish that approval delays were a widespread pain point.

<b>Challenge:</b> Maintaining sufficient review and safety without unnecessary coordination overhead.

<b>Engineer goal:</b> Ensure that proposed changes have been reviewed before they are applied.

<b>Opportunity:</b> Clearly show approval status, required actions, and the context reviewers need.


<h3>Stage 5 : Test and validate in lower-risk environments</h3>

<b>Activities observed:</b> Engineers deploy to lab, experimental, development, staging, or pre-production environments. They validate system behavior and monitor for issues. Some participants described monitoring periods of one to two weeks.

<b>Automation involvement:</b> Deployment pipelines, Argo Workflows, and automated checks execute portions of testing and deployment.

<b>Human involvement:</b> Engineers interpret test results, investigate failures, and decide whether production rollout can begin.

<b>Where the workflow can break</b>

An unexpected issue during testing interrupts the planned rollout. Engineers must investigate, fix the problem, and validate the change again.

<b>Challenge:</b> Determining whether testing has provided enough confidence to continue.

<b>Engineer goal:</b> Confirm that the change works before applying it to production.

<b>Opportunity:</b> Consolidated test results, environment health, and clear readiness indicators.

<h3>Stage 6 : Roll out changes across production clusters</h3>

<b>Activities observed: </b> Engineers deploy changes progressively, sometimes starting with one production cluster before continuing to the remaining fleet.

<b>Automation involvement:</b> Pipelines, Argo Workflows, and controllers execute rollout steps where supported.

<b>Human involvement:</b> Engineers supervise progress, decide when to advance, and handle cluster-specific exceptions.

<b>Where the workflow can break</b>

A cluster-specific failure or unexpected behavior may interrupt the rollout. The engineer must determine whether the issue affects one cluster or requires stopping the broader deployment.

<b>Challenge:</b> Coordinating staged updates and understanding rollout status across multiple clusters.

<b>Engineer goal:</b> Apply maintenance changes across production clusters while limiting operational risk.

<b>Opportunity:</b> Fleet-wide rollout tracking with cluster status, rollout stages, and pause/resume controls.

<h3>Stage 7 : Monitor and validate maintenance outcomes</h3>

<b>Activities observed:</b> Engineers review cluster health, alerts, component status, and system behavior after maintenance. Some monitor production clusters for an extended period before continuing.

<b>Automation involvement: </b> Monitoring tools, health checks, and alerts provide ongoing feedback.

<b>Human involvement:</b> Engineers interpret the results and determine whether the rollout can continue or maintenance is complete.

<b>Where the workflow can break: </b>

Unexpected alerts, degraded health, or unclear validation results require further investigation. Engineers may need to compare affected clusters with healthy ones to understand the problem.

<b>Challenge:</b> Understanding whether a maintenance change was successful across the entire fleet.

<b>Engineer goal:</b> Confirm that changes have been applied successfully and that clusters remain healthy.

<b>Opportunity:</b> A consolidated validation view that connects rollout progress, cluster health, and post-change alerts.

<h3>Stage 8 : Troubleshoot and recover from exceptions</h3>

<b>Activities observed:</b> Engineers investigate unresolved alerts, deployment failures, missing configurations, unsupported updates, and cluster-specific problems.

<b>Automation involvement:</b> Monitoring and diagnostic tools assist investigation. Some issues can be resolved automatically.

<b>Human involvement:</b> Engineers investigate error messages, configurations, recent changes, and infrastructure behavior. They apply fixes, retest, and decide how to proceed.

<b>Where the workflow breaks</b>

The normal automated process cannot continue without investigation or correction. Missing configuration, unclear instructions, or differences between clusters can increase the work required to identify the cause.

<b>Challenge: </b> Identifying the root cause of failures across tools, configurations, and multiple clusters.

<b>Engineer goal:</b> Identify and resolve problems that interrupt maintenance.

<b>Opportunity:</b> An investigation workspace connecting errors, logs, alerts, configuration history, and differences between healthy and affected clusters.


<h3>Stage 9 : Document, improve, and automate recurring work</h3>

<b>Activities observed:</b> Engineers document findings, improve alerts, refine processes, introduce Renovate, move manual tasks into controllers, and improve self-service workflows.

<b>Automation involvement:</b> Newly introduced automation reduces repeatable manual tasks in future maintenance cycles.

<b>Human involvement:</b> Engineers identify recurring issues, determine which activities can be automated, and update documentation and operational processes.

<b>Where the workflow can break</b>

Improvements may remain incomplete when manual fixes, configuration changes, or incident learnings are not consistently documented or incorporated into repeatable processes.

<b>Challenge:</b> Turning individual troubleshooting experiences into lasting operational improvements.

<b>Engineer goal:</b> Reduce future maintenance effort and prevent repeated problems.

<b>Opportunity:</b> Link incident findings, maintenance history, documentation updates, and automation improvements.

<h2>Key insights</h2>

<b>Insight : 1 Maintenance is a continuous process, not just upgrading Kubernetes clusters</b>

Engineers continuously monitor and maintain their multi-cluster environments. Maintenance involves detecting problems, reviewing updates, managing infrastructure, troubleshooting issues, and improving existing processes.

<b>Insight: 2 Engineers use gradual upgrades and testing to reduce production risks</b>

Engineers avoid applying major changes to all production clusters at once. They commonly test updates in lower-risk environments and gradually deploy them to production.

<b>Insight : 3 Automation handles routine maintenance, but human intervention remains essential</b>

Engineers automate repeatable maintenance activities, while human involvement is still needed for risk assessment, approvals, troubleshooting, and unexpected problems.

<b>Insight : 4 Troubleshooting is the biggest interruption to an otherwise repeatable maintenance workflow</b>

Engineers generally follow structured maintenance processes, but unexpected failures interrupt those processes and require manual investigation.

<b>Insight : 5 Engineers continuously improve maintenance processes, but configuration consistency and documentation remain challenges</b>

Engineers learn from maintenance incidents and try to improve their workflows through better automation, configuration management, alerts, and documentation.


<h2>Conclusion</h2>

The maintenance analysis reveals that Kubernetes multi-cluster maintenance is not a single upgrade process. It is a continuous operational journey involving monitoring, risk assessment, infrastructure configuration, testing, progressive rollout, validation, troubleshooting, and ongoing improvement.

Across the participant workflows, automation supports repeatable activities, while engineers remain involved in evaluating risks, approving changes, interpreting system health, and resolving unexpected problems.

The main distinction is between the normal maintenance path, where changes progress through established processes, and the exception path, where failures or uncertainty require investigation and recovery.


<b>Core research finding:</b> Effective multi-cluster maintenance depends on visibility across clusters, confidence in change safety, clear human intervention points, and the ability to investigate and recover from exceptions.



