<h2>Deployment Analysis and Results</h2>

We asked engineers to describe their end-to-end deployment workflows to better understand their processes, experiences, and challenges throughout the deployment journey.

We kept this question open-ended, allowing participants to freely share their experiences, challenges, and pain points without limiting their responses to predefined topics.

During the discussions, we encouraged engineers to identify areas where they experienced difficulties, explain which steps required manual intervention, and highlight where automation was already in place or could potentially improve their workflows.

This approach helped us gain deeper insights into real-world deployment practices, identify workflow inefficiencies, and uncover opportunities to improve the developer experience in Kubernetes multi-cluster environments.


<h2>There is no single multi-cluster deployment workflow</h2>

<b>Pattern : 1 Application Deployment</b>

Several workflows focused on moving application changes from source code into Kubernetes.
A typical pattern was:

<b>Code change → CI/CD → Build artifact → Deployment configuration → Kubernetes → Validation</b>

Some workflows additionally progressed through development, staging, and production environments.

<b>Pattern : 2 GitOps-Based Deployment</b>

Several participants used Git repositories as the source of deployment configuration and tools such as Argo CD or Flux to reconcile those configurations with Kubernetes clusters.

A typical workflow was:

<b>Configuration change → Git repository → Argo CD/Flux detects change → Kubernetes deployment → Health validation</b>

<b>Pattern : 3 Cluster Provisioning</b> 

Some participants described creating the Kubernetes cluster itself rather than deploying an application to an existing cluster.

These workflows included infrastructure provisioning, cluster creation, platform bootstrap, networking, access configuration, and validation.

A representative pattern was:

<b>Cluster request → Infrastructure → Kubernetes cluster → Platform bootstrap → Configuration → Validation → Handoff</b>

<b>Pattern : 4 Customer-Specific Deployment</b>

Some deployments depended on customer-specific configuration.

A representative pattern was:

<b>Customer requirements → Configuration/template → Generated deployment configuration → Deployment workflow → Kubernetes</b>

<b>Pattern : 5 Progressive Multi-Cluster Deployment</b>

Some organizations gradually deployed changes across clusters or regions and used monitoring results to decide whether the deployment should continue.

A representative workflow was:

<b>Build → Safety checks → Initial deployment → Health monitoring → Additional clusters/regions → Completion</b>

<b>Pattern : 6 Fleet and Cluster Lifecycle Management</b>

Other workflows focused on maintaining clusters rather than deploying individual applications.

These included:

<b>Cluster templates → Cluster lifecycle → Kubernetes upgrades → Add-on management → Multi-cluster orchestration</b>


<h2>Common Deployment workflows pattern among participants </h2>

<b>Step : 1 Configure</b>

The workflow begins by defining what needs to be deployed.

Configuration can include: Application source code, Helm charts, YAML manifests, Customer-specific configuration, Infrastructure definitions, Cluster templates, Environment configuration

Configuration is therefore an important foundation of the deployment process.

<b>↓</b>

<b>Stage 2: Determine the Target</b>

The deployment must then be associated with the appropriate destination.

Depending on the workflow, the target can include:

- Development cluster
- Staging cluster
- Production cluster
- Customer cluster
- Kubernetes fleet
- Region
- Cloud provider
- Specific subset of clusters
  
In multi-cluster environments, deployment involves not only defining what should change but also where that change should occur.

<b>↓</b>

<b>Stage 3: Trigger the Workflow</b>

Deployment initiation varies across participants.

Triggers include:

- Commit to the main branch
- Merge into the default branch
- Creation of a feature/preview branch
- Configuration merge
- CI/CD pipeline
- Cluster request
- GitOps synchronization
- Git-based events appear repeatedly in the workflows.

<b>↓</b>

<b>Stage 4: Build or Generate Deployment Artifacts</b>

Before deployment, systems may generate or package the resources required for deployment.

Examples include:

- Building application code
- Creating container images
- Generating Kubernetes manifests
- Packaging Helm charts
- Generating customer-specific configuration
- Creating infrastructure resources
- Generating deployment workflows

This stage often connects source control and CI/CD systems with Kubernetes deployment systems.

<b>↓</b>

<b>Stage 5: Deploy or Provision</b>

The next stage executes the requested change.

Tools appearing in the participant workflows include:

- Argo CD
- Argo Rollouts
- Flux
- Helm
- Terraform
- OpenTofu
- Cluster API
- Ansible
- CircleCI
- Azure DevOps pipelines
- Custom/internal deployment systems

The data demonstrates that multi-cluster deployment commonly spans multiple systems rather than relying on one deployment tool.

<b>↓</b>

<b>Stage 6: Validate Deployment and Application Health</b>

Deployment execution does not necessarily indicate that the application or platform is functioning correctly.

Participants described validation using:

- Kubernetes health checks
- Argo CD deployment status
- Application logs
- Observability platforms
- Metrics
- Automated tests
- Monitoring gates
- Infrastructure validation
- Human verification
- This creates an important distinction between:
- Deployment completed

and

- Application/platform verified as healthy

Some participants explicitly described checking multiple systems after deployment to determine whether the application was operating successfully.

<b>↓</b>

<b>Stage 7: Progress the Deployment</b>

Several workflows progressively move changes through environments, clusters, or regions.

Examples include:

<b>Development → Testing → Staging → Production</b>

or:

<b>Initial cluster/region → Health check → Additional clusters/regions</b>

This staged approach allows teams to validate changes before expanding deployment scope. Production deployment may also include manual approval.

<b>↓</b>

<b>Stage 8: Recover or Complete</b>

When validation succeeds, the rollout can continue or complete.

When problems occur, participants described several possible responses:

- Automatic rollback
- Manual rollback
- Restore previous configuration
- Roll forward with another commit
- Investigate the affected cluster
- Stop or delay further rollout
- Perform manual troubleshooting

Failure handling varies more significantly than the basic deployment execution process.

<h2>Challenge or Break! In the deployment flow </h2>

We will explain what happens at each stage of the common deployment journey, identify where challenges or breakdowns occur, and highlight the specific activities that involve automation and human intervention.

<b>Stage 1 : Prepare application and configuration</b>

Participant Example : An engineer prepares a customer-specific configuration file. A Helm template is used to generate the configuration for that customer.

<b>Automation:</b> Helm templates generate the final configuration using customer-specific inputs.

<b>Human intervention</b> Engineers prepare or update the source configuration and decide which changes are required.

<b>Potential breakpoint</b> Different customer configurations must remain correct and consistent. The participant workflow establishes configuration variation, but not a specific failure at this stage.

Stage result: Deployment configuration is prepared.

<b>Stage 2 : Select deployment targets</b>

Participant Example : Engineers select clusters and environments in an Argo CD-based deployment workflow.

<b>Automation:</b> Some systems determine deployment destinations automatically.

<b>Human intervention:</b> Engineers may choose target clusters, environments, or deployment scope.

<b>Potential breakpoint:</b> Incorrect targeting could affect the wrong clusters. This is a risk inferred from the targeting activity, not a reported incident in the workflow summary.

Stage result: The intended deployment targets are identified.

<b>Stage 3 : Trigger deployment</b>

Participant Example : CircleCI detects a preview branch and starts the process that generates manifests and commits them to a configuration repository.

<b>Automation:</b> Branch detection, pipeline initiation, and subsequent GitOps processing.

<b>Human intervention:</b> A developer creates the branch, commits changes, or initiates a release.

<b>Potential breakpoint:</b> The workflow crosses from Git into CI/CD and configuration repositories, creating a need to trace the change across systems.

Stage result: The deployment workflow starts.

<b>Stage 4 : Build and generate artifacts</b>

Participant Example :The system builds the service, pushes the container image, replicates it across regions, and packages a Helm chart.

<b>Automation:</b> Build, publishing, replication, and packaging are automated in this participant's workflow.

<b>Human intervention:</b> Engineers may need to investigate when a build or artifact-generation process fails, although the supplied steps do not explicitly document such a failure.

<b>Potential breakpoint:</b> Dependencies between the build system, image registries, and deployment system create possible failure points.

Stage result: Deployment artifacts are ready.

<b>Stage 5 : Deploy to Kubernetes clusters</b>

Example from Participant 3: Argo CD pulls configuration, the custom layer generates manifests, and Argo CD deploys the relevant resources. Argo Rollouts manages the rollout.

<b>Automation:</b> Manifest synchronization and deployment execution.

<b>Human intervention:</b> Engineers become involved when rollout results require investigation or an exception decision.

<b>Breakpoint:</b> A deployment may succeed in some clusters and fail in others, requiring further action.

Stage result: The application is deployed or rolling out across selected clusters.

<b>Stage 6 : Validate deployment and application health</b>

Participant Example : Engineers check Argo CD status, review observability information, and manually verify health across clusters.

<b>Automation:</b> Kubernetes status, tests, monitoring and health signals.

<b>Human intervention:</b> Review logs and metrics, interpret application behavior, and manually verify cluster health where required.

<b>Breakpoint:</b> Deployment status alone is insufficient to establish application health, and one participant explicitly described manual verification across clusters.

Stage result: Engineers or automated gates determine whether the application is healthy enough to continue.

<b>Stage 7 : Progress across environments and clusters</b>

Participant Example : The deployment system gradually rolls out a change across clusters and regions using automated monitoring gates.

<b>Automation:</b> Scheduled or progressive deployment and monitoring gates.

<b>Human intervention:</b> Some workflows require production approval or manual decisions about whether to proceed.

<b>Breakpoint:</b> Different clusters may be at different rollout stages, making the overall deployment state harder to understand.

Stage result: The change progresses across the intended deployment scope.

<b>Stage 8 : Handle failure and recovery</b>

Participant Example : Engineers manually decide how to handle partial failures and may create a new commit to roll forward., The system detects a failure, triggers rollback, and restores the previous configuration.

<b>When a deployment fails:</b>

<b>↓</b>

(a = Automated recovery : Detect failure → Roll back → Restore configuration ) or (b = Human-led recovery : Investigate partial failure → Decide → Roll forward or take other action) 

<b>↓</b>

Validate recovered state

<b>Breakpoint:</b> Recovery is not handled the same way in every workflow. Partial failure can require human decisions even when deployment execution is automated.

Stage result: The deployment is completed, recovered, or left pending further investigation.

<h2>Before - During - After deployment challenges mentioned by engineers </h2>

<b>Before Deployment : Configuration and Targeting Complexity</b> 

Engineers must determine: What should be deployed? Which configuration applies? Which customer? Which environment? Which cluster? Which region?

<b>During Deployment : Orchestration Complexity</b>

The workflow may span:

Git → CI/CD → Registry → Helm → Argo CD/Flux → Kubernetes → Infrastructure systems
Engineers therefore depend on several interconnected systems.


<b>After Deployment : Visibility and Decision Complexity</b>

After execution, engineers may need to determine: Did the deployment succeed? Did it succeed everywhere? Which clusters failed? Is the application actually healthy? Should rollout continue? Should it stop? Should the team roll back or roll forward?

For multi-cluster environments, the post-deployment stage deserves particular attention because one deployment can produce different states across different clusters.

<h2>UX Recommendations for Deployment: </h2>

<b>Automation + Control </b> → Automate repetitive work while preserving human decisions.

<b>Failure & Recovery</b> → Make partial failures understandable and actionable.

<b>Visibility</b> → See deployment state across all clusters and workflows

<b>Deployment + Health</b> → Connect rollout progress with operational health.

<b>Reduced Complexity</b> → Bring information from fragmented systems into one contextual deployment experience.








