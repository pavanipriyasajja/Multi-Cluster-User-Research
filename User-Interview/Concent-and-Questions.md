<h2>Consent form information</h2>

Thank you for taking the time to participate in this semi-structured interview!

The Kubernetes SIG Multicluster UX Working Group is conducting a user interview to gather insights from users, operators, and developers on how multicluster Kubernetes environments are being used in practice. Your feedback will help us understand current usage patterns, pain points, and areas for improvement.

Whether you're just starting with multicluster setups or managing complex environments, your input is incredibly valuable and will help shape future design directions, feature priorities, and community resources. There are no right or wrong answers, I’m just looking to understand your reality.

This is an official user research of SIG Multicluster of Kubernetes.The user interview will take approximately 45-60 minutes to complete.

With your permission, I’ll record this session for research purposes only.

All research data will be fully anonymized. Your name, company, email, and all direct verbatim responses and recordings will never be shared in our findings. We will only report aggregated insights and anonymous, generic quotes to protect your privacy. These aggregated key insights and/or anonymous, generic quotes will be shared publicly on SIG Multicluster meetings, Kubecon or related convention presentations, and/or research papers on the Kubernetes or SIG-Multicluster website.

Raw research data will be shared only with the User Research team and SIG Multicluster SIG-Chairs (who are responsible for running operations and processes governing the SIG) for the purposes of the research study only.

Participation is completely voluntary. Is that okay?



<h2>Question</h2>

<b>1. Can you tell me about your role and responsibilities? Specifically, how do you interact with multi-cluster environments in your day-to-day work?</b>

<b>2. Can you walk me through your typical deployment workflow across multiple clusters, from preparing a deployment to verifying that everything is running successfully?</b>

Followup questions: 

- Which steps are manual?
- Where do deployment failures most commonly occur? (Future question for application developers: Application on top of kubernetes and Creating clusters on kuberentes..)
- What makes deployments across multiple clusters more difficult than managing a single cluster?
- How do application teams interact with the platform team during deployments?

<b>3. When something goes wrong in a multi-cluster environment, can you walk me through or explain how you investigate and troubleshoot the issue? (process)</b>

Followup questions: 

- Which tools do you usually open first?
- How do you determine which cluster is affected?
- What information is usually missing?
- Which part of troubleshooting takes the longest? 

<b>4. Can you describe your day-to-day operational tasks for maintaining multiple clusters? </b>

Followup questions: 

- Documentation challenges?
- How do you manage upgrades?
- Configuration changes?
- Policy updates?
- Cluster inventory?
- What tasks require the most manual effort?
- Which maintenance activities become harder as the number of clusters grows?


<b>5. From your perspective, what are the biggest challenges developers face when working in a multi-cluster environment? </b>

Followup: 

- Onboarding a teammate
- Where do developers typically struggle?
- Which requests do developers frequently bring to the platform team?
- What creates the most operational complexity?
- Which workflows generate the most support tickets?


<b>6. How does your team collaborate when managing multiple clusters?</b>

Followup questions: 

- Where does communication usually break down?
- How are responsibilities divided?
- Are ownership boundaries always clear?
- What would improve collaboration?


<b>7. Can you tell me about a recent multi-cluster incident that was particularly difficult to diagnose or resolve?</b>

Followup: 

- What happened?
- How did you investigate the issue?
- What made it difficult?
- Looking back, what would have helped you resolve it more quickly?


<b>8. How do you currently organize and manage your growing number of clusters? </b>

Followup: 

- How do you track cluster metadata?
- How do you ensure policy consistency across clusters?
- How do you decide where workloads should run?
- What governance challenges do you experience?
- Multi tenancy challenges? Cross cluster issues?

<b>9. Looking at your current tooling and workflows, where do you feel the biggest gaps exist today?</b>

Followup: 

- Which tools work well together?
- Which tools create additional complexity?
- Are there workflows that require switching between multiple dashboards or systems?
- What information do you wish was available in one place?


<b>10. If you could improve one aspect of multi-cluster Kubernetes management, what would it be and why? </b>

Followup: 

- What problem would this solve?
- How would it improve your daily workflow?
- Who would benefit the most?
- Is this something you've seen requested by others?

<b>11. what capabilities or improvements do you think are most important for the future of multi-cluster Kubernetes management?</b>

Followup: 

- What would make managing multiple clusters significantly easier?
- Is there anything we haven't discussed that you think is important?





















