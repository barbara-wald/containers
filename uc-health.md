---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}




# Healthcare use cases for {{site.data.keyword.cloud_notm}}
{: #cs_uc_health}

These use cases highlight how workloads on {{site.data.keyword.containerlong}} benefit from the public cloud. They have secure compute on isolated bare metal, easy spin-up of clusters for faster development, migration from virtual machines, and data sharing in cloud databases.
{: shortdesc}


## Healthcare provider migrates workloads from inefficient VMs to Ops-friendly containers for reporting and patient systems
{: #uc_migrate}

An IT Exec for a healthcare provider has business reporting and patient systems on-premises. Those systems go through slow enhancement cycles, which leads to stagnant patient service levels.  
{: shortdesc}

To improve patient service, the provider looked to {{site.data.keyword.containerlong_notm}} and {{site.data.keyword.contdelivery_full}} to reduce IT expenses and accelerate development, all on a secure platform. The provider’s high-use SaaS systems, which held both patient record systems and business report apps, needed updates frequently. Yet the on-premises environment hindered agile development.  The provider also wanted to counteract increasing labor costs and a decreasing budget.

They started by containerizing their SaaS systems and putting them in the cloud. From that first step, they went from over-built hardware in a private data center to customizable compute that reduces IT operations, maintenance, and energy. To host the SaaS apps, they easily designed Kubernetes clusters to fit their CPU, RAM, and storage needs.  Another factor for decreased staff costs is that IBM manages Kubernetes, so the provider can focus on delivering better customer service. 

Accelerated development is a key win for the IT Exec. With the move to public cloud, Developers can experiment easily with Node.js SDK, pushing changes to Development and Test systems, scaled out on separate clusters. Those pushes were automated with open toolchains and {{site.data.keyword.contdelivery_full}}. Updates to the SaaS system no longer languished in slow, error-prone build processes. The Developers can deliver incremental updates to their users, daily or even more frequently.  Also, logging and monitoring for the SaaS systems, especially how the patient front-end and back-end reports interact, rapidly integrate into the system. Developers don’t waste time building complex logging systems, just to be able to troubleshoot live systems.

Security first: With bare metal for {{site.data.keyword.containerlong_notm}}, the sensitive patient workloads now have familiar isolation but within the flexibility of public cloud. From that core, Vulnerability Advisor provides scanning:
* Image vulnerability scanning
* Policy scanning based on ISO 27k

Secure patient data leads to happier patients.

### Context
{: #uc_migrate_context}

* Technical debt, which is coupled with long release cycles, is hindering the provider’s business-critical patient management and reporting systems.
* Their back-office and front-office custom apps are delivered on-premises in monolithic virtual machine images.
* They need to overhaul their processes, methods, and tools but don’t know quite where to start.
* Their technical debt is growing, not shrinking, from an inability to release quality software to keep up with market demands.
* Security is a primary concern, and this issue is adding to the delivery burden, which causes even more delays.
* Capital expense budgets are under tight control, and IT feels they don't have the budget or staff to create the needed testing and staging landscapes with their in-house systems.

### Solution
{: #uc_migrate_solution_model}

Compute, storage, and I/O services run in the public cloud with secure access to on-premises enterprise assets. Implement a CI/CD process and other parts of the IBM Garage Method to dramatically shorten delivery cycles.

#### Step 1: Secure the compute platform
{: #uc_migrate_step1}

* From that core, Vulnerability Advisor provides image, policy, container, and packaging scanning vulnerability scanning.
* Consistently enforce policy-driven authentication to your services and APIs with a simple Ingress annotation. With declarative security you can ensure user authentication and token validation by using {{site.data.keyword.appid_short_notm}}.

#### Step 2: Lift and shift
{: #uc_migrate_step2}

* Migrate virtual machine images to container images that run in {{site.data.keyword.containerlong_notm}} in the public cloud.
* Provide standardized DevOps dashboards and practices through Kubernetes.
* Enable scaling compute resources for batch and other back-office workloads that run infrequently.
* Use {{site.data.keyword.SecureGatewayfull}} to maintain secure connections to on-premises DBMS.
* Private data center / on-premises capital costs are greatly reduced and replaced with a utility computing model that scales based on workload demand.

#### Step 3: Microservices and Garage Method
{: #uc_migrate_step3}

* Reconfigure apps into a set of cooperative microservices. That set runs within {{site.data.keyword.containerlong_notm}} that is based on functional areas of the app with the most quality problems.
* Use {{site.data.keyword.cloudant}} with customer provided keys for caching data in the cloud.
* Adopt continuous integration and delivery (CI/CD) practices so that Developers version and release a microservice on its own schedule as needed. {{site.data.keyword.contdelivery_full}} provides for workflow toolchains for CI/CD process along with image creation and vulnerability scanning of container images.
* Adopt the agile and iterative development practices from the IBM Garage Method to enable frequent releases of new functions, patches, and fixes without downtime.

Technical solution
* {{site.data.keyword.containerlong_notm}} 
* {{site.data.keyword.cloudant}}
* {{site.data.keyword.SecureGatewayfull}}
* {{site.data.keyword.appid_short_notm}}

For sensitive workloads, the clusters can be hosted in {{site.data.keyword.containerlong_notm}} for Bare Metal. By using industry-standard containers technology, apps can initially be re-hosted on {{site.data.keyword.containerlong_notm}} quickly without major architectural changes. This change provides the immediate benefit of scalability.

They can replicate and scale the apps by using defined rules and the automated Kubernetes orchestrator. {{site.data.keyword.containerlong_notm}} provides scalable compute resources and the associated DevOps dashboards to create, scale, and tear down apps and services. By using Kubernetes's deployment and runtime objects, the provider can monitor and manage upgrades to apps reliably.

{{site.data.keyword.SecureGatewayfull}} is used to create a secure pipeline to on-premises databases and documents for apps that are re-hosted to run in {{site.data.keyword.containerlong_notm}}.

{{site.data.keyword.cloudant}} is a modern NoSQL database suitable a range of data-driven use cases from key-value to complex document-oriented data storage and query. To minimize queries to the back-office RDBMS, {{site.data.keyword.cloudant}} is used to cache the user's session data across apps. These choices improve the front-end app usability and performance across the apps on {{site.data.keyword.containerlong_notm}}.

Moving compute workloads into the {{site.data.keyword.cloud_notm}} isn't enough though. The provider needs to go through a methods transformation as well. By adopting the practices of the IBM Garage Method, the provider can implement an agile and iterative delivery process that supports modern DevOps practices like CI/CD.

Much of the CI/CD process itself is automated with IBM's Continuous Delivery service in the Cloud. The provider can define workflow toolchains to prepare container images, check for vulnerabilities, and deploy them to the Kubernetes cluster.

### Results
{: #uc_migrate_results}

* Lifting the existing monolithic VMs into cloud-hosted containers was a first step that allowed the provider to save on capital costs and begin learning modern DevOps practices. 
* Reconfiguring key monolithic apps to a set of fine-grained microservices greatly reduced delivery time for patches, bug fixes, and new features.
* In parallel, the provider implemented simple time-boxed iterations to get a handle on the existing technical debt.

## Research nonprofit securely hosts sensitive data while it grows research with partners
{: #uc_research}

A Development Exec for a disease research nonprofit has academic and industry researchers who can't easily share research data. Instead, their work's isolated in pockets across the globe due to regional compliance regulations and centralized databases.
{: shortdesc}

{{site.data.keyword.containerlong_notm}} delivers secure compute that can host sensitive and data processing on an open platform. That global platform is hosted in near-by regions. So it's tied to local regulations that inspire patients’ and researchers’ confidence that their data is both protected locally and makes a difference in better health outcomes.

### Context
{: #uc_research_context}

Securely hosting and sharing disease data for Research Nonprofit

* Disparate groups of researchers from various institutions don’t have a unified way to share data, slowing down collaboration.
* The security concern adds to the collaboration burden that causes even less shared research.
* Developers and Researchers are spread across the globe and across organizational boundaries, which make PaaS and SaaS the best option for each user group.
* Regional differences in health regulations require some data and data processing to remain within that region.

### Solution
{: #uc_research_solution}

Securely hosting and sharing disease data for Research Nonprofit.

The research nonprofit wants to aggregate cancer research data across the globe. So they create a division that is dedicated to solutions for their researchers.

* INGEST - Apps to ingest research data. Researchers today use spreadsheets, documents, commercial products, and proprietary or home-grown databases to record research results. This situation is unlikely to change with the nonprofit's attempt to centralize data analysis.
* ANONYMIZE - Apps to anonymize the data. SPI must be removed to comply with regional health regulations.
* ANALYZE - Apps to analyze the data. The basic pattern is to store the data in a regular format and then to query and process it by using AI and machine learning (ML) technology, simple regressions, and so forth.

Researchers need to affiliate with a regional cluster, and apps ingest, transform, and anonymize the data.
1. Syncing the anonymized data across regional clusters or shipping them to a centralized data store
2. Processing the data, by using ML like PyTorch on bare metal worker nodes that provide GPUs

INGEST
:   {{site.data.keyword.cloudant}} is used at each regional cluster that stores researchers’ rich data documents and can be queried and processed as needed. {{site.data.keyword.cloudant}} encrypts data at rest and in transit, which complies with regional data-privacy laws.

:   {{site.data.keyword.openwhisk}} is used to create processing functions that ingest research data and store them as structured data documents in {{site.data.keyword.cloudant}}. {{site.data.keyword.SecureGatewayfull}} provides an easy way for {{site.data.keyword.openwhisk}} to access on-premises data in a safe and secure manner.

:   Web apps in the regional clusters are developed in nodeJS for manual data entry of results, schema definition, and research organizations affiliation. IBM Key Protect helps to secure access to {{site.data.keyword.cloudant}} data, and IBM Vulnerability Advisor scans app containers and images for security exploits.

ANONYMIZE
:   Anytime new data document is stored in {{site.data.keyword.cloudant}}, an event is triggered, and a Cloud Function anonymizes the data and removes SPI from the data document. These anonymized data documents are stored separate from the "raw" data that is ingested and are the only documents that are shared across regions for analysis.

ANALYZE
:   Machine learning frameworks are highly compute-intensive, and thus the nonprofit set up a global processing cluster of bare-metal worker nodes. Associated with this global processing cluster is an aggregated {{site.data.keyword.cloudant}} database of the anonymized data. A cron job periodically triggers a Cloud Function to push anonymized data documents from the regional centers to the global processing cluster's {{site.data.keyword.cloudant}} instance.

:   The compute cluster runs the PyTorch ML framework, and machine learning apps are written in Python to analyze the aggregated data. In addition to ML apps, researchers in the collective group also develop their own apps that can be published and run on the global cluster.

:   The nonprofit also provides apps that run on non-bare metal nodes of the global cluster. The apps view and extract the aggregated data and the ML app output. These apps are accessible by a public endpoint, which is secured by the API Gateway to the world. Then, researchers and data analysts from everywhere can download data sets and do their own analysis.

Developers started by deploying their research-sharing SaaS apps in containers with {{site.data.keyword.containerlong_notm}}. They created clusters for a Development environment that allow worldwide Developers to collaboratively deploy app improvements quickly.

Security first: The Development Exec chose bare metal to host the research clusters. With bare metal for {{site.data.keyword.containerlong_notm}}, the sensitive research workloads now have familiar isolation but within the flexibility of public cloud. Because this nonprofit also has a partnership with pharmaceutical companies, app security is crucial. Competition is fierce, and corporate espionage is possible. From that secure core, Vulnerability Advisor provides scanning.
* Image vulnerability scanning
* Policy scanning based on ISO 27k

Secured research apps lead to increased clinical trial participation.

To achieve global availability, the Dev, Test, and Production systems are deployed across the globe in several data centers. For HA, they use a combination of clusters in multiple geographic regions as well as multizone clusters. They can easily deploy the research app to Frankfurt clusters to comply with the local European regulation. They also deploy the app within the United States clusters to ensure availability and recovery locally. They also spread the research workload across multizone clusters in Frankfurt to ensure that the European app is available and also balances the workload efficiently. Because researchers are uploading sensitive data with the research-sharing app, the app’s clusters are hosted in regions where stricter regulations apply.

Developers focus on domain problems, by using existing tools: Instead of writing unique ML code, ML logic is snapped into apps, by binding {{site.data.keyword.cloud_notm}} services to clusters. Developers are also freed up from infrastructure management tasks because IBM takes care of Kubernetes and infrastructure upgrades, security, and more.

Compute, storage, and apps run in public cloud with secure access to research data across the globe, as warranted. Compute in clusters is tamper-proof and isolated to bare metal.

Technical solution:
* {{site.data.keyword.containerlong_notm}}
* {{site.data.keyword.openwhisk}}
* {{site.data.keyword.cloudant}}
* {{site.data.keyword.SecureGatewayfull}}

#### Step 1: Containerize apps by using microservices
{: #uc_research_step1}

* Create a Node.js app or deploy an example.
* Structure apps into a set of cooperative microservices within {{site.data.keyword.containerlong_notm}} based on functional areas of the app and its dependencies.
* Deploy research apps to containers in {{site.data.keyword.containerlong_notm}}.
* Provide standardized DevOps dashboards through Kubernetes.
* Enable scaling compute resources for batch and other research workloads that run infrequently.
* Use {{site.data.keyword.SecureGatewayfull}} to maintain secure connections to existing on-premises databases.

#### Step 2: Use secure and performance driven compute
{: #uc_research_step2}

* ML apps that require higher-performing compute are hosted on {{site.data.keyword.containerlong_notm}} on Bare Metal. This ML cluster is centralized, so each regional cluster doesn't have the expense of bare metal workers; Kubernetes deployments are easier too.
* Vulnerability Advisor provides image, policy, container, and packaging scanning vulnerability scanning.

#### Step 3: Ensure global availability
{: #uc_research_step3}

* After Developers build and test the apps in their Development and Test clusters, they use the IBM CI/CD toolchains to deploy apps into clusters across the globe.
* Built-in HA tools in {{site.data.keyword.containerlong_notm}} balance the workload within each geographic region, including self-healing and load balancing.
* With the toolchains and Helm deployment tools, the apps are also deployed to clusters across the globe, so workloads and data meet regional regulations.

#### Step 4: Data sharing
{: #uc_research_step4}

* {{site.data.keyword.cloudant}} is a modern NoSQL database suitable a range of data-driven use cases from key-value to complex document-oriented data storage and query.
* To minimize queries to the regional databases, {{site.data.keyword.cloudant}} is used to cache the user's session data across apps.
* This choice improves the front-end app usability and performance across apps on {{site.data.keyword.containerlong_notm}}.
* While worker apps in {{site.data.keyword.containerlong_notm}} analyze on-premises data and store results in {{site.data.keyword.cloudant}}, {{site.data.keyword.openwhisk}} reacts to changes and automatically sanitizes data on the incoming feeds of data.
* Similarly, notifications of research breakthroughs in one region can be triggered through data uploads so that all researchers can take advantage of new data.

### Results
{: #uc_research_results}

* Microservices greatly reduce time to delivery for patches, bug fixes, and new features. Initial development is fast, and updates are frequent.
* Researchers have access to clinical data and can share clinical data, while they comply with local regulations.
* Patients who participate in disease research feel confident that their data is secure and making a difference, when it is shared with large research teams.




