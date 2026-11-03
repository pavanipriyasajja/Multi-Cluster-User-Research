<h2>Developer Biggest Challenge</h2>

We asked engineers about the biggest challenges they face when working with Kubernetes multi-cluster environments. Based on their responses, we identified the following key themes.

<b>Insight 1 : Multi-cluster complexity is largely absorbed by platform engineering teams.</b>

Application developers may experience relatively simple deployment workflows because platform teams build and maintain the underlying abstractions. However, platform engineers must manage the complexity of infrastructure, tooling, configuration, and operations across clusters.

<b>Insight 2 : Lack of standardization creates repeated engineering effort.</b>

Differences in cluster configurations, tooling, and infrastructure force engineers to develop custom solutions, handle environment-specific exceptions, and repeatedly solve similar problems.

<b>Insight 3 : Developers need service-centric experiences rather than cluster-centric workflows.</b>

Developers often need to know which cluster hosts their application before they can troubleshoot or manage it. Service-based navigation could reduce the need to understand cluster topology.

<b>Insight 4 : Fragmented information increases troubleshooting effort.</b>

Engineers must navigate disconnected monitoring systems and cluster contexts to find relevant information, delaying investigation and requiring additional coordination.

<b>Insight 5 : Infrastructure changes require stronger consistency and validation mechanisms.</b>

Configuration differences across environments make platform changes unpredictable. Engineers need ways to identify differences, assess risks, and validate changes before progressing across clusters.

<h2>Multi-tenancy common flow and challenges</h2>

Common pattern identified among the participants

<b>Shared cluster → Namespace isolation → Policy/access controls → Stronger isolation for sensitive workloads → Dedicated cluster when necessary</b>

<b>Key finding:</b> Cluster sharing reduces infrastructure duplication but increases isolation and policy complexity.

<b>Insight:</b> Participants commonly share clusters across teams, services, or customers, while using namespaces and policies as isolation boundaries. Sensitive or untrusted workloads may require stronger isolation or dedicated clusters. The main challenge is consistently maintaining security, access, ownership, and communication boundaries across mixed tenancy models.

<h2>One important aspect to improve multicluster operations</h2>

<b>Theme 1: Fragmented visibility across clusters</b>

- Engineers lack a unified view of cluster health, operational status, and changes.
- Monitoring information is distributed across multiple tools and clusters.
- Comparing configurations and resource states requires manual investigation.
- Collecting near real-time information across clusters introduces significant data volume and infrastructure costs.
- Environment and network boundaries complicate centralized monitoring.

<b>Theme: 2 Lack of standardized multi-cluster management</b>

- Different organizations use different approaches to multi-cluster management.
- Existing solutions do not always provide stable, reusable building blocks.
- Cluster inventory information lacks a consistent data model.
- Tools and controllers use incompatible information-sharing mechanisms.
- Engineers repeatedly build custom integrations and management components.
- Engineers lack clear guidance on selecting appropriate multi-cluster approaches.

<b>Theme 3: Complex fleet-wide operations</b>

- Applying changes across multiple clusters requires careful coordination.
- Engineers need to select clusters, control rollout order, and monitor progress.
- Running administrative commands separately across clusters increases manual effort.
- Large fleets require scalable provisioning, configuration, and add-on management.
- Incorrect fleet-wide commands can introduce widespread operational risk.

<b>Theme 4: Cross-cluster access and execution complexity</b>

- Engineers need to access multiple clusters securely.
- Cross-cloud credential management and delegated permissions are complicated.
- Engineers must manually identify which clusters contain particular services.
- Existing tools do not always understand relationships between teams, services, namespaces, and clusters.
- Executing operations across clusters introduces security and operational risks.

<b>Theme 5: Difficult troubleshooting and configuration comparison</b>

- Engineers manually compare Kubernetes resources across clusters.
- Configuration differences can be difficult to identify.
- Troubleshooting requires switching between cluster contexts.
- Engineers need to determine whether failures originate from Kubernetes configuration or application behavior.

<b>Theme 6: Cluster lifecycle and scaling complexity</b>

- Provisioning and connecting additional clusters involves multiple steps.
- Engineers need standardized templates for creating and updating clusters.
- Managing add-ons across thousands of clusters is difficult.
- Large fleets require resilient control planes and efficient management tools.

<b>Theme: 7 Cross-cluster state movement</b>

- Transferring application state between clusters is difficult.
- State movement within a cluster can also be complicated.
- Engineers need simpler mechanisms for cross-cluster communication and state migration.
























