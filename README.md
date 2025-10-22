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







  
  
  





