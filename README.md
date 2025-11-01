# Microsoft-Azure-Cloud-Services
Azure fundamentals and concepts

This notes is my personal understanding of the AZ-900 course based upon a Youtube Tutotrial.
This is useful for people who are trying to understand basic Azure concepts and trying to participate for AZ-900 certificate exam.

People with no prior clouding knowledge or no idea of basic Azure concepts can start with this course. This is where we begin the journey in the cloud.
Concepts covered:
> Cloud Concepts
> Core Azure Services
> Security, Privacy, Compliance and trust
> Azure pricing and support

Study Areas: (Useful inforamtion for People who are trying for Azure certificate)
Describe Cloud Concepts (15 to 20%)
Describe core Azure Services (30-35%)
Describe Security, Privacy, Compliance and trust(25-30%)
Describe Azure pricing and support(20-25%)


* Introduction to Cloud Computing

Cloud computing is the delivery of computing services over the internet. Computing services include common IT infrastructure such as virtual machines, storage, databases, and networking. Cloud services also expand the traditional IT offerings to include things like Internet of Things (IoT), machine learning (ML), and artificial intelligence (AI).

Because cloud computing uses the internet to deliver these services, it doesn’t have to be constrained by physical infrastructure the same way that a traditional datacenter is. That means if you need to increase your IT infrastructure rapidly, you don’t have to wait to build a new datacenter—you can use the cloud to rapidly expand your IT footprint.
Refernce Link: https://learn.microsoft.com/en-us/training/modules/describe-cloud-compute/3-what-cloud-compute

Basically, it is a delivery model for services like storage(databases), compute power (linux, mac, windows), networking, analytics.

Key Characterstics of Cloud:
> Scalability: It is a process of adding or removing resources
> Elasticity: ability of system to scale dynamically
> Agility: the ability to react quickly (allocate and deallocate resources)
> Fault tolerance: ability of system to remian up and running during component and service failures
> Disaster Recovery: creating 2 copies of application (system ability to recover from any unexpected disaster)
> High Availability: High availability is the ability to keep services running for extended periods of time with very little downtime.


* Principles of Economics of Scale

  This will explain the cost of Azure.
  > Cost per unit(service) lowers as the company grows Due to increase in efficiency)


* Capital and Operational Expenditures

  Expenditure is an action of spending your company funds.

  CapEX means :
  > Own Infrasturcture
  > Big initial investment
  > Lots of maintenance is required

  OPEx maens:
  > Renting Infrasturcture (Cloud perfectly fits)
  > No initial investment, pay for what you use.
  > Minimal maintenance (mostly handled by cloud providers)
  <img width="955" height="347" alt="image" src="https://github.com/user-attachments/assets/71210280-5661-443a-9ff8-1291e963fc5d" />

* Consumption Based Cloud model
 
  Key Characterstics:
  > No upfront costs 
  > No wasted resources
  > Pay for additional resources when needed
  > stop paying at anytime
  > Multiple pricing components per service
  > very granular usage measurement

* Cloud Service Models (Iaas v/s Paas v/s Saas)

  Infrastructure as Service (IaaS):
  All the layers that are directly related to the hardware ( virtualization, servers, networking, storage)

  Platform as Service (PaaS):
  All the software required to run the application (Runtime, middleware, OS)

  Software as Service(Saas):
  Application and data is software layer

* Public, Private and Hybrid cloud deployment models

  Public Cloud: Everything runs on cloud provider hardware, No Local hardware (don't own our own hardware/datacenter). Hosting everyhting in public cloud
  <img width="1042" height="506" alt="image" src="https://github.com/user-attachments/assets/061d2e3a-0045-4535-9b84-80539e147957" />

  Private Cloud: You host everything in your own datacenter. You're the one maintainging all teh hardware.
  <img width="1022" height="478" alt="image" src="https://github.com/user-attachments/assets/a39ebe60-ce4d-4997-9f93-d22e81edcb56" />

  Hybrid Cloud: Will take advantage of both public and private clouds.
  <img width="995" height="465" alt="image" src="https://github.com/user-attachments/assets/b9bd3fb1-ad98-4257-90cb-6354e3da194d" />

* Azure Physical Infrastructure

  Data Center: Data center is a physical facitlity that hosts for group of networked servers. A typical data center has its own power, cooling and networking infrastructure.
  Region: It is a geographical area on the planet. It is the location for your services. Some of the services are not available in all regions. Azure is globally avaialble in 50+ regions. They were like government(US DOD, US Gov Virginia etc) and partnered(China East,            China North etc) regions.
  Availability Zone: It is a regional feature, grouping of physically seperate facilitites. These are designed to protect from data center failures.If one zone goes down,then others keep working. Not all regions support availability zone. But, if a region supports it ...then they do have 3 or more zones. It is build from one or more datacenters.
                      2 service categories: Zonal services (VM's , disks etc) and Zone redundant services (like SQL, storage etc).
  Microsoft also provides "Region Pair"- which is a group of different regions. So, if one region goes down the other regions in the pair still work. These pairs are static (you cannot choose which regions to pair). But these pairs are done for regions within same        geography. Some services have platform-provided replication. Planned updates accross the pairs. Data residency is maintained for disaster recovery. Below are few examples for 'region pairs'
  <img width="1044" height="532" alt="image" src="https://github.com/user-attachments/assets/961a53dc-1bf3-490e-8308-c2c417f8de46" />

  Geographies: All regions or region pairs are grouped into geographies. Each geography describes discrete market. Typically contains 2 or more regions. Ensure data residency, sovereignty, resiliency and compliance requirements are met. These are fault tolerant to                     protect from region wide failures.Each region belongs to only one geography.

* Resources, Resource Groups and Resource Manager

  Resources: It can be any SQL or Web or staorage that Azure provides to cusotmers. It is an object that is used to manage services in Azure. It represents service lifecycle. All resources can be represented in JSON template (they have 4 properties like Type,                        APIversion, Name, Location)
  Resource Groups: It is just grouping resources. We can group by type, lifecycle, department, billing, location or combination of those. Each resource must be in one, and only one resource group. They have their own location assigned. BUt, resources can reside in                         different locations. Resources can be moved between resource groups. Resource groups cannot be nested.
  Resource Manager: It is a management layer for all resources and resource groups. It has unified language. It is also responsible for checking your rights/privileges with Azure directory. It controls access and resources.

* Azure Compute Services (VMs, VM Scale Set, App Service, Functions, ACI, AKS)
  Compute Services is a category of services in Azure allowing u to build and run cloud based services.
  Virtualization: On Physical machine you will install Operating System and additionally install virtualization software with several VM's. It is emualization of physical machines. It gives ability to create virtual hardware configuration per machine/app.
                  Additonally different Operating systems per machine/app.
  And, virtulaization in cloud is done through Azure Virtual Machines: You either bribe microsoft VM's (like Windows, Linux or Oracle) or you can request your own VM's (with your own system, config, runtime, apps and services)

  VM's are Iaas . You are responsible for OS and software. Support marketplace and custom images. Best suited for custom software requiring custom configuration (or) lift-and-shift scenarios. They can run any apps/scenarios.
  VM scale stes : are Iaas. But they are set of identical VM's created from same image. They built-in scaling features is wsed for designing manual and auto-scaled workloads like web services, batch processing etc.
  Containers: They don't have their won OS(Use hosts OS). They emulate OS and lightweight. Respond quick to demand changes. Designed for almost any scenario.
  First service for containers is Container Instances.
  Container Instances are Simplest and fastest way to run a container in Azure. It is Paas and serveless containers. Designed for small and simple web apps/services, background jobs and scheduled scripts.
  Azure Kubernetes Services: It is an open source container orchestration platform. It is Paas, highly scalable and customizable. It is designed for high scale container deployments.
  App Service: Designed as enterprise grade web application service. It is another Paas. Supports mulitple programming languages and containers.
  Azure functions/function apps: It is Paas. Serverless. 2 hosting/pricing models (consumption-based plan & dedicated plan). Designed for nano or micro services.
  Below is the summary of Azure Compute Services:
  <img width="1091" height="433" alt="image" src="https://github.com/user-attachments/assets/e0024b5a-2504-4758-8669-ea5467b00eb0" />
  <img width="1011" height="532" alt="image" src="https://github.com/user-attachments/assets/7aea567e-0b7f-4916-8e5e-f200a76420e6" />
  <img width="1063" height="599" alt="image" src="https://github.com/user-attachments/assets/4a3ed43e-6e3e-49f9-a2fb-a4a42e482e82" />

* Networking Services
  It is a category of services that allows to connect cloud and on-premises resources. Helpful for protection and monitor services along with application delivery.
  Azure Virtual Network: It is a group of Vm's or subnets. We can connect Virtual network's together using "VNET PEERING" or "VPN GATEWAY".
  <img width="1167" height="558" alt="image" src="https://github.com/user-attachments/assets/c6cac9e0-ae50-4cbf-bd63-7f83a67022bd" />
  VPN Gateway: It is used to connect 2 VM's or a VM and On-Premise resource.
  <img width="1004" height="337" alt="image" src="https://github.com/user-attachments/assets/f81f72dc-432d-470d-9e25-9f3f160ffcc7" />
  Azure Load Balancer: We can have 2 different load balancers, one with public internet traffic control known as 'Public Load balancer' and other private IP allowing private connectivity know as 'Internal Load Balancer'
  <img width="1118" height="478" alt="image" src="https://github.com/user-attachments/assets/860be8b9-fda6-4750-bee5-2696c0a929dd" />
  Applciation Gateway: If a traffic is a web traffic(HTTP) then we want to replace load balancer with application gateway. (It is nothing but a replacement of Public Load balancer)
  <img width="964" height="527" alt="image" src="https://github.com/user-attachments/assets/349c99b9-5fae-4a10-86e4-9902fc5dab5a" />
  Content Delivery Network(CDN): allows deliver of web content to user to minimize latency. And all the content is prresent in POP(points of presence) locations.
  <img width="1139" height="480" alt="image" src="https://github.com/user-attachments/assets/d152285c-b4ed-47cf-91ba-b90e3b5d9291" />

* Azure Storage Services
  
  Types of data
  Structured Data: Your data is laid out so nicely that it can be described using a specific schema. For each row of the table you can define properties and any relationship between tables.
  Semi Structure Data: You still have a table but each row need not to be followed any specific schema. Where each row can have its own properties.
  Un-Structures Data: Data like images, movies, binary application files that donot follow any structure and donot follow any particular schema.

  Azure Blob Storage: Any un-structured data called BLOB. And you can put those BLOB's into any container. Azure BLOB STORAGE is more than one container.
  It is designed for storage of any files (Binary Large Object File).
  They are 3 storage tiers: HOT (Used for frequently accessed data), COOL (You're accepting lower availability and lower performance files while maintaing higher durability), ARCHIVE (rarely if-ever accessed data)
  
  <img width="957" height="558" alt="image" src="https://github.com/user-attachments/assets/6607b52b-bc18-4aae-958e-71343ffcacc3" />

  Azure Queue Storage: Small Service and significant service when building application. It is used to store small pieces of data(messages) and designed for scalable asynchronus processing.
  Azure Table Storage: This is designed for semi-structured data in mind. It is storage of multiple tables. This is also called no SQL database's. We use this kind of storage when there is no need for foreign joins, foreign keys, realtionships or strict schema. This is designed for fast access.
  Azure File Storage: It is similar to BLOB storage. In file storage we use Files instead of BLOB's. The only difference is the way you access them, in file storage you accesss by SMB protocol. Storage for files accessed via shared drive protocols. Designed to extend on-premises file shares or implement lift-and-shift scenarios.
  Azure Storage Account: It is a group of services that include blob, queue, file and table storage. They are designed to store messages, text, files and semi-sturctured data. It is highly scalable and highly durable.It is cheapest per GB storage.
  Azure disk storage: Disk emulation in cloud. Persistent storage for VM's. It comes with different types, sizes and perforamce tiers. It allows customers to manage or unmanage the disks.
  <img width="1027" height="463" alt="image" src="https://github.com/user-attachments/assets/0d4f6709-a569-45e2-96ea-00a80382792a" />

* Database Services in Azure
  
  Azure Cosmos DB: It is Similar to semi-structured data. But instead of Tables this one will have Collections and instead of table storage it is known as Cosmos DB. It has ability to replicate geographically.
  Once you select the region then your db will replicate the region's db. It can read and write globally. This db is low latency. It is globally distributed NOSQL (semi-structured data) db service. It is schema-less db. abiltiy to multiple APIs(SQL, MongoDB, Cassanda, Gremlin, Table storage). It is designed for higly responsive and mulit-regional applications.

  Azure SQL DB: Storing structure data. It is relational db service in the cloud(Paas)(DBaas-database as Service). Structured data service defined using schema and relationships. Rich query capabilities.It has high-performance, reliable, fully managed and secure dbfor building applications.
<img width="1007" height="503" alt="image" src="https://github.com/user-attachments/assets/d8f86dcc-beb4-47c7-854d-9c5a5524d856" />
Azure SQl:
<img width="967" height="498" alt="image" src="https://github.com/user-attachments/assets/528e140a-ca19-49e0-be19-d538b15c7496" />

<img width="995" height="477" alt="image" src="https://github.com/user-attachments/assets/4037ae03-a9ef-4985-b6f2-bf4c8847036a" />

* Azure MarketPlace
  It is similar to online shop. You can select ur products you need add it to ur bpx and buy it.
  Where u purchase azure services or out of office box solutions. Inside azure marketplace you can find products made by microsoft or third party services. The products consisits of Paas, Saas, and Iaas.<img width="992" height="562" alt="image" src="https://github.com/user-attachments/assets/d2d63ccb-6e7b-4bcb-905f-e41a1159ef52" />

* Azure IOT Services
  
  Internet of things: It is a network of internet connected devices embedded in everyday objects enabling sending and receiving data such as settings and telemetry.
  Azure IOT Hub: ALlows for bi-directional service between cloud and IOT devices. Allows developers to take advantage of providing insigihts, developing and monitoring .
  <img width="903" height="456" alt="image" src="https://github.com/user-attachments/assets/7a7787d2-b2f9-45c8-be13-de9626b21792" />
  Azure IOT Central: IOT central as service provides u set of templates to build applications.Users donot need to build apps from  scratch.
  <img width="782" height="413" alt="image" src="https://github.com/user-attachments/assets/daf319bf-780f-4784-ae8d-d105d2a6d626" />

  Azure Sphere: It is not a service along. It is set of compnents used to build IOT. Azure sphere also delivers Azure sphere security service.
  <img width="747" height="307" alt="image" src="https://github.com/user-attachments/assets/6d5f21f9-e644-4333-aa48-f1abc09e951c" />
  <img width="925" height="346" alt="image" src="https://github.com/user-attachments/assets/4f44a3b6-f5cd-40f3-9ad8-36dcdc0233ed" />

* Azure Big Data & Analytics Services
  Big data is a field of technology that helps with extraction, processing and analysis of information that is too large or complex to deal with traditional software.
  Azure Synapse Anslytics: It is big data analytics plateform (PAAS). It consits of multiple components (SPark, synapse SQL) . It also have Synapse pipelines with studio included
  <img width="922" height="555" alt="image" src="https://github.com/user-attachments/assets/92bb830f-46be-423d-b331-99682f72808c" />

  Azure HDinsight: Felxible multi-purpose big data platform (Paas). It supports multiple technologies(Hadoop, spark, kafka, HBase, Hive, Storm, Machine Learning)

  <img width="932" height="553" alt="image" src="https://github.com/user-attachments/assets/529feb77-333b-4ade-aa3a-23cd683c5988" />
  Azure Databricks: It is quite similar to HDinsight apart the clusters we create are depended upon apache spark & spark. Main purpose is to help data transforamtion at large scale.
  It is a big data colloboration platform (Paas). It provides unified workspace for notebook, cluster, data , access management and colloboration.It is based on Spark Integrates well with common azure data         services.
  <img width="913" height="541" alt="image" src="https://github.com/user-attachments/assets/db50bfe8-2e00-4df4-81f2-160b31e56117" />
  <img width="1000" height="386" alt="image" src="https://github.com/user-attachments/assets/1c558494-149d-4169-ab55-a6ea375b09d3" />
* Azure AI Services
  AI is a simulation of human intelligence and capabilities by computer software. Machine Learning is a subcategory of AI where a computer software is taught to draw conclusions and make predicitons from data.
  Azure Machine Learning: It is end-to-end cloud based platform for creating, managing and publishing ML models. It is Paas. Top level resource is know as ML workspace. ML studio is a web portal for end-2-end development. Key features of axure ML are notebook(using python and  R), Automated ML (run multiple parameters/algorithms combinations), designer (graphical interface for no-code development, it enables customers build their ML pipelines visually), data & compute (management of storage and compute resources) and Pipelines (orchestrate data model training, deployemnet and management tasks).

  <img width="996" height="463" alt="image" src="https://github.com/user-attachments/assets/8afc27c0-db38-46bd-bdab-0552abb838ca" />

* Azure Serverless Computing Services
  
  Serverless Computing: Is cloud-hosted execution environment that allows customers to run their applications in cloud while completely abstracting underlying infrastructure.
  Azure Functions: It is a service that allows cusotmers to build applications using code. Cutosmers create code package them and sends to fucntion app and later it is distributed among multiple app node's .
  It is simply serverless coding platfrom(functions as a service, Faas). Designed for nano-service architectures and event-based applications. It quiclkly scales up and down, highly scalable. Supports popular languages and frameworks (like .NET, .NET Core, Jave, Node.js, Python, Powershell etc).
  Azure Logic Apps: This service is used to build workflows interface that represent business or cross functional. These are serverless enterprise integration service (Paas), it has 200+ connectors for popular services. This service is specifically desinged for orchestration of business processes, integration workflows for applications, data, systems and services. It is no-code solution.
  Azure Event Grid: It is a service for routing messages. Fully managed serverless event routing service. Uses publish-subscribe model. Designed for event based and naer real time applications. It supports lot of built-in events from common azure services.
  <img width="1015" height="412" alt="image" src="https://github.com/user-attachments/assets/1070e539-2b81-4811-9f7f-dded9418f3f3" />

* Azure DevOps Solutions
  
  DevOps: It is a set of pracitices that combine both development(dev) and Operations(Ops). It's goal is to shorten development life cycle by providing continuous integration and delivery capabilities while        ensuring high quality of deliverables. 
  Azure DevOps: It is a collection of services for building solutions using DevOps practices. It provides services like boards, pipelines, repos, test plans, artifacts. It is extensible with maketplace over 1000 of available apps. Evolved from TFS through VSTS.

  <img width="960" height="457" alt="image" src="https://github.com/user-attachments/assets/b283cef3-8f06-4939-a1a9-fd1c08476c34" />

  Azure DevTest Labs: It provides ability for users to create VM's so that they can very quickly develop things and test things. It is a service sandbox environment for developers/testers (Paas). It provides ability to quick setup of self-managed virtual machines , preconfigured templates for VMs and plenty of additional artifacts (tools, custom actions, apps). Additonally u will have lab policies (quotas, sizes, auto-shutdowns). You can share and automate labs via custom images.
  <img width="1030" height="541" alt="image" src="https://github.com/user-attachments/assets/461765af-1689-4c70-bbed-cd5f064ee65f" />
  <img width="1012" height="301" alt="image" src="https://github.com/user-attachments/assets/c8453121-7439-4b38-9474-c1381d3ffec0" />

* Azure Tools
  
  Azure Portal: It is a public web-based interface for management of Azure Platform. Designed for self-service. It is quite customizable, and designed to help customer for simple tasks.
  Azure Powershell: It is simply a module, designed for automation and mulit-platform with PowerSHell Core. It is simple use (Connect-Azaccount - log into azure, Get-AzResourceGroup - list resource groups, New- AzResourceGroup - to create new resource group, New-AzVm - to create VM) (It is moslty benefical for people who use WINDOWS)
  Azure CLI(Command Line Interface): This is more beneficial for people with LINUX. CLI for Azure and also desinged for automation. It is multi-platform(Python). SImple to use (az login - to login to Azure, az group List - list resource groups, az group create - create new resource group, az vm create - create VM). It is just a tool for native OS terminal.
  Azure Cloud Shell: It is cloud-based scripting environment and completely free. It supports both Azure powershell and azure CLI. It does of dozen of additional tools. And, it does have multiple client interfaces like Azure portal integration (portal.azure.com), Shell Portal (shell.azure.com), Visual stuidon code extension and Windows Terminal, Azure Mobile app and Microsoft docs integration.
  <img width="1045" height="413" alt="image" src="https://github.com/user-attachments/assets/91fd9531-9df9-460c-9485-33ae052fae1f" />

* Azure Advisor
  It is our personalized consultant service, designed to provide reommendations and best practices for Cost (SKU sizes, idel services, reserved instances etc), Security (MFA settings, vulnerability settings, agent installations etc), Reliability (redundancy settings, soft delete on blobs etc), Performance(SKU sizes, SDK versions, IO throttling etc), operational excellence (service health, subscription limits etc). It comes with actionable recommendations. And all these are for free.

* Azure Security Groups
  
  Network Security Groups (NSG): It is designed to filter traffic to(inbound) and from (outbound) Azure resources located in Azure Virtual network. This filtering is controlled by rules and it does have ability to have multiple inbound and outbound rules. These rules are created by specifying Source/Destination (IP addresses, service tags, application security groups), protocol (TCP, UDP any), Port and Direction (inbound, outbound), Priority (order of evaluation)
  Application Security Group (ASG): It is a feature that allows grouping of VM's located in Azure virtual network.Desinged to reduce the maintenance effort (assign ASG insted of explicit IP addresses)

  <img width="1144" height="378" alt="image" src="https://github.com/user-attachments/assets/e08f48f4-9b42-4803-8020-3ebccb979d8c" />

* User Defined Routes (UDR) with Route Tables

  Routing is a process of finding/selecting a path for a traffic between one or more servers in one or across multiple networks. User defined routes are custom-defined routes. These are designed to override Azure default routing or add new routes. This is managed by Azure Route table resource, and route tables are designed to associate with zero or more Virtual network subnets.


* Azure Firewall
  
  Firewall is a network security service that allows customers to monitor and control incoming and outgoing traffic.
  Azure Firewall is a managed, cloud-based firewall service(Paas). It is build with high-availability and highly scalable. It allows to filter inbound and outbound traffic. Supports for FQDN (Fully Qualified Domain Name). And, it is fully integrated with Azure monitor   for logging and analytics.


* Azure DDoS Protection (Distributed Denial of Service)

  DOS is denial of Service. It is a cyber attack with intent to cause temporary or indefinite disruption of service. They are many types of DoS, but their main goal is to stop your service.
  Distributed Denial Of Service is one of them.
  DDoS Protection: It is in Azure. Designed to detect malicious traffic and block it while allowing legitimate users to connect, prevent additional osts for auto-scaling environments. It is divided into 2 tiers - Basic (automatically enabled for Azure Platform), Standard (additional mitigation & montioring capabilities for Azure Virtual Network services). Standard tiers uses ML to analyze traffic pattern.

* Azure Identity Services

  Identity: In general, it is the fact of being something or someone. A user with a username and password. Also applications or other servers with secret keys or certificates.
  Process of verification/assertion of identity is called Authentication.
  Authorization: The process of ensuring that only authenticated identities get access to resources for which they have been granted access. 
  Access Management: The process of controlling, verifying, tracking and managing access to authorized users and applications.
  Azure AD: It is our identity & access management service in Azure.   Identity management - users, groups, applications. Access management - subscriptions, resource groups, roles, role assignments, authentication & authorization settings etc. It is used by multiple cloud platforms like azure, microsoft 365, office 365 etc. It can sysn with on-premises Active directory.
  Multi-factor authentication: Process of presenting two or more pieces of evidence to prove one's identitiy. They ar emany factor types like Knowledge factor (Something you know, ex: password, pin), Possession factor (Something you have, ex: Phone, token, card, key), Physical Characteristic Factor (Something you are, ex: fingerprint, voice, face, eye irirs), Location (Somewhere you are, ex: GPS location). And all this Supported by Azure AD by default(simple on-off switch).

* Azure Security Center

  Centralized/unified infrastructure and platform security management service. Natively embedded in Azure services. It is integrated with Azure advisor. It has 2 tiers - Free (Azure defender OFF): included in all azure services, provides continuous assessments, security score, and actioanble security recommendations, Paid (Azure Defender ON) - hybrid security, threat protection alerts, vulnerability scanning, just in time VM access, etc.

* Azure Key Vault

  It is secured storage for keys, secrets and certificates. I tis managed service for securing sensitive information (Application/platform )(PaaS). It is Highly integrated with other azure services (VMs, Logic Apps, Data Factory , Web Apps etc). Centralization. Access monitoring and logging.
  














  

  







  
  
  





